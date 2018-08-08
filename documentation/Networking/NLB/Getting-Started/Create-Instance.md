# 创建网络负载均衡实例

可根据具体的业务场景选择购买、配置公网、内网类型的网络负载均衡实例。

## 内网负载均衡

- 内网负载均衡只能在京东云内网使用，可以转发对京东云内网具有访问权限的客户端请求。创建内网负载均衡的步骤如下：

	![创建内网ALB设置](https://github.com/jdcloudcom/cn/blob/master/image/Networking/NLB/NLB-058.png)

	创建负载均衡时选择“暂不购买”公网IP，完成相关资源配置，则默认创建内网类型的负载均衡实例。
	
## 公网负载均衡

- 公网负载均衡可以将来自公网的访问请求流量转发至后端虚拟服务器，公网负载均衡需要单独购买公网IP，步骤如下：

	![创建公网ALB设置](https://github.com/jdcloudcom/cn/blob/master/image/Networking/NLB/NLB-059.png)

	购买负载均衡时选择公网IP（不超过公网IP可创建配额），系统会自动为负载均衡创建并绑定一个公网IP。

## 内网负载均衡转为公网负载均衡

- 京东云支持内网、公网负载均衡类型互转，内网负载均衡可通过绑定公网IP转换为公网类型的负载均衡，公网负载均衡解绑公网IP后可转换为内网类型的负载均衡。

	![内网ALB转为公网ALB设置](https://github.com/jdcloudcom/cn/blob/master/image/Networking/NLB/NLB-060.png)

	