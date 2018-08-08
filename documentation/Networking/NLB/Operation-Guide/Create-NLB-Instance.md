# 创建网络负载均衡

1. 通过菜单-网络-负载均衡进入负载均衡列表页。

 	![NLB列表页](../../../../../image/Networking/NLB/ALB-015.png)

1. 点击“创建”新建一个负载均衡实例。

1. 选择地域，注意和需要选择的私有网络所在地域保持一致。

1. 选择可用区，负载均衡将在选定可用区部署实例资源，强烈推荐选用多个可用区。

1. 选择所属私有网络、子网信息，负载均衡只能将流量转发至同私有网络下的后端服务器。

1. 选择公网IP计费方式：按固定带宽或者按使用流量计费；如创建内网负载均衡，可选择暂不购买，也可以在负载均衡创建完成后再绑定公网IP。

1. 填写负载均衡名称、描述。

1. 选择创建数量，可创建数量受负载均衡、公网IP、子网等配额限制，配额信息可通过概览页查看。

1. 页面右侧确认配置及费用信息，点击 **立即购买**。

	![ALB创建设置](https://github.com/jdcloudcom/cn/blob/master/image/Networking/ALB/ALB-016.png)

 	![ALB创建设置](https://github.com/jdcloudcom/cn/blob/master/image/Networking/ALB/ALB-017.png)

1. 确认订单信息并完成支付，创建负载均衡实例。

 	![ALB确认订单](https://github.com/jdcloudcom/cn/blob/master/image/Networking/ALB/ALB-018.png)

1. 完成负载均衡实例创建；因资源创建需一定时间（通常为几秒），可手动刷新列表页查看状态。

 	![ALB创建完成](https://github.com/jdcloudcom/cn/blob/master/image/Networking/ALB/ALB-019.png)
