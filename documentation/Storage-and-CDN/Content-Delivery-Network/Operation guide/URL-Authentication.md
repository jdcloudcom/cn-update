# URL鉴权说明

京东云CDN 支持参数鉴权，用户可以根据自己的业务情况，选择合适的鉴权方式，来实现对源站资源的有效保护。（目前直播只有参数鉴权）

1.参数鉴权方法

1.1   加密 URL 构成

https://DomainName/Path/Filename?参数& auth_token=expire-uniqid-rand-signature

signature =md5sum("uri-expire-uniqid-rand-private_key")

1.2   鉴权字段描述

1.3   原理说明

l  CDN服务器拿到请求后，首先会判断请求中的 expire  是否小于当前时间，如果小于，则认为过期失效并返回HTTP 403错误。如果 expire 大于当前时间，则构造出一个同样的字符串(参考以下signature构造方式)。然后使用MD5算法算出 new_signature ，再和请求中带来的 signature  进行比对。比对结果一致，则认为鉴权通过，返回文件。否则鉴权失败，返回HTTP 403错误。

l  new_signature  是通过以下字符串计算出来的：

origin_ signature = "uri-expire-uniqid-rand-private_key " （uri是用户的请求对象相对地址，不包含参数）

new_signature = md5sum(origin_ signature)

1.4   示例说明

1. 通过请求对象:

https://cdn.example.com/video/standard/1K.html?fa=121&jd=121

2. 密钥设为：jdcloud1234 (由用户自行设置)

3. 鉴权配置文件失效日期为：2020年06月18日00:00:00,计算出来的秒数为1592409600

4. 则CDN服务器会构造一个用于计算signature的签名字符

/video/standard/1K.html-1592409600-0-0-jdcloud1234"

5. CDN服务器会根据该签名字符串计算signature:

signature = md5sum("/video/standard/1K.html-1592409600-0-0-jdcloud1234") =06d97bc9e43ded48d991994006cfa127

6. 则请求时url为：

https://cdn.example.com/video/standard/1K.html ?fa=121&jd=121&auth_token=1592409600-0-0-06d97bc9e43ded48d991994006cfa127

计算出来的signature与用户请求中带的 signature =06d97bc9e43ded48d991994006cfa127值一致，于是鉴权通过。




2.路径鉴权法

2.1 加密 URL 构成

https://DomainName/deadline/ md5sum("uri-deadline-password")/Path/Filename?参数

2.2 鉴权字段描述


2.3 原理说明

l  CDN服务器拿到请求后，首先会判断请求中的 deadline 是否小于当前时间，如果小于，则认为过期失效并返回HTTP 403错误。如果 deadline大于当前时间，则构造出一个同样的字符串(参考以下sstring构造方式)。然后使用MD5算法算出 HashValue ，再和请求中带来的 md5hash 进行比对。比对结果一致，则认为鉴权通过，返回文件。否则鉴权失败，返回HTTP 403错误。

l  HashValue 是通过以下字符串计算出来的：

sstring = "uri-deadline-Password" （uri是用户的请求对象相对地址，不包含参数）

HashValue = md5sum(sstring)

2.4   示例说明

1. 通过请求对象:

https://cdn.example.com/video/standard/1K.html ?fa=121&cc=121

2. 密钥设为：jcloud1234 (由用户自行设置)

3. 鉴权配置文件失效日期为：2020年06月18日00:00:00,计算出来的秒数为1592409600

4. 则CDN服务器会构造一个用于计算Hashvalue的签名字符

/video/standard/1K.html-1592409600-jcloud1234"

5. CDN服务器会根据该签名字符串计算HashValue:

HashValue = md5sum("/video/standard/1K.html-1592409600-jcloud1234") = 8afb0900782e14c35214ccda534a3679

6. 则请求时url为：

https://cdn.example.com/1592409600/8afb0900782e14c35214ccda534a3679/video/standard/1K.html? fa=121&cc=121

计算出来的HashValue与用户请求中带的 md5hash = 8afb0900782e14c35214ccda534a3679 值一致，于是鉴权通过。
