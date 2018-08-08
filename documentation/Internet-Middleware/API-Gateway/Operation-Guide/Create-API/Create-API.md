# 创建API

API分组是网关的基础服务单元并实现对外开放，而每个API分组下包含了具体的API。创建API的过程即API提供者定义API的过程。


## 操作步骤：

1.在API分组列表页中，找到需要创建API的分组

 ![API分组管理](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/apigroup-1.png)
 
点击该分组行的操作 **管理API**，进入“API列表”页

 ![API列表](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/apigroup-apilist.png)


2. 在“API列表”页面，点击 **新建API** ，进入创建API页面。

![新建API](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/apigroup-addapi.png)


3. 新建成功后，再点击新增的API进入API详情页，并进行高级选项配置。该项目可选配，但当需要进行实际发布时该信息项需要配置。

![高级配置](https://github.com/jdcloudcom/cn/blob/edit/image/Internet-Middleware/API-Gateway/apigroup-addapi-advane.png)
  
  
4.填写API信息后，点击保存，即新建完成。

5.目前系统支持API导入功能，点击API列表页的 **导入API**  ,导入即可。注意，导入文件需要符合swagger 2.0规范。具体规范请参照：
![swagger 2.0规范](http://editor.swagger.io/)  
