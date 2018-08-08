# 兼容接口

|云存储支持的api|api简介|描述|
|-|-|-|
|GET Service（List Bucket）|获取一个User下的所有Bucket|兼容 [GET Service](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTServiceGET.html)|
|PUT Bucket|新建一个Bucket，默认的权限为Private|兼容 [PUT Bucket](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketPUT.html)|
|HEAD Bucket|确定一个Bucket是否存在且有权利访问<br>如果Bucket存在且有权利访问，则返回200 OK。如果指定的bucket不存在，则返回404 Not Found|兼容 [HEAD Bucket](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketHEAD.html)|
|GET Bucket（List Object）|获取一个Bucket下面Object的信息（兼容Version2）|兼容 [GET Bucket](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/v2-RESTBucketGET.html)|
|DELETE Bucket|删除指定的Bucket|兼容 [DELETE Bucket](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketDELETE.html)|
|PUT Object|上传一个Object到OSS|兼容 [PUT Object]|(https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTObjectPUT.html)
|GET Object|获取一个Object的Meta及数据，可以获取全部数据或者使用Range指定获取部分数据|兼容 [GET Object](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTObjectGET.html)|
|HEAD Object|获取一个Object的Meta|兼容 [HEAD Object](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTObjectHEAD.html)|
|DELETE Object|删除一个Object|兼容 [DELETE Object](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTObjectDELETE.html)|
|Initiate MultiPart Upload|初始化一个多步上传的任务|兼容 [Initiate MultiPart Upload](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/mpUploadInitiate.html)|
|Upload Part|上传一个Part到OSS|兼容 [Upload Part](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/mpUploadUploadPart.html)|
|Complete MultiPart Upload|把上传的多个part合并成一个Object|兼容 [Complete MultiPart Upload](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/mpUploadComplete.html)|
|Abort MultiPart Upload|终止一次多步上传任务|兼容 [Abort MultiPart Upload](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/mpUploadAbort.html)|
|List Parts|获取指定uploadid已经上传成功的part的信息|兼容 [List Parts](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/mpUploadListParts.html)|
|List MultiPart Uploads|获取一个Bucket下面正在进行的多步上传任务|兼容 [List MultiPart Uploads](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/mpUploadListMPUpload.html)|
|GET Bucket policy|获取指定的Bucket上的policy|兼容 [GET Bucket policy](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketGETpolicy.html)|
|PUT Bucket policy|为指定的Bucket上添加或编辑policy|兼容 [PUT Bucket policy](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketPUTpolicy.html)|
|DELETE Bucket policy|删除指定的Bucket上的policy|兼容 [DELETE Bucket policy](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketDELETEpolicy.html)|
|PUT Bucket acl|在指定的Bucket上设置acl|兼容 [PUT Bucket acl](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketPUTacl.html)|
|GET Bucket acl|获取指定的Bucket的acl|兼容 [GET Bucket acl](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketGETacl.html)|
|PUT Bucket cors|为指定的Bucket添加CORS规则|兼容 [PUT Bucket cors](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketPUTcors.html)|
|GET Bucket cors|获取指定的Bucket的CORS规则|兼容 [GET Bucket cors](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketGETcors.html)|
|DELETE Bucket cors|删除指定的Bucket的CORS规则|兼容 [DELETE Bucket cors](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketDELETEcors.html)|
|PUT Bucket website|为指定的Bucket添加静态网站托管规则（注：接口兼容，但规则细节与S3有出入）|兼容 [PUT Bucket website](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketDELETEcors.html)|
|GET Bucket website|获取指定的Bucket的静态网站托管规则（注：接口兼容，但规则细节与S3有出入）|兼容 [GET Bucket website](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketDELETEcors.html)|
|DELETE Bucket website|删除指定的Bucket的静态网站托管规则（注：接口兼容，但规则细节与S3有出入）|兼容 [DELETE Bucket website](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketDELETEcors.html)|
|Put Object Copy|拷贝一个在OSS上已经存在的object成另外一个object|未支持：x-amz-copy-source-if-match，<br>x-amz-copy-source-if-none-match，<br>x-amz-copy-source-if-unmodified-since，<br>x-amz-copy-source-if-modified-since，<br>x-amz-tagging-directive<br>x-amz-storage-class<br>支持STANDARD和REDUCED_REDUNDANCY<br>参考：[PUT Object - Copy](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTObjectCOPY.html)|
|Upload Part Copy|通过从一个已存在的Object中拷贝数据来上传一个Part。|未支持：x-amz-copy-source-if-match，<br>x-amz-copy-source-if-none-match，<br>x-amz-copy-source-if-unmodified-since，<br>x-amz-copy-source-if-modified-since<br>参考：[Upload Part - Copy](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/mpUploadUploadPartCopy.html)|
|Delete Multiple Objects|支持用户通过一个HTTP请求删除同一个Bucket中的多个Object|未支持：version<br>参考：[Delete Multiple Objects](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/multiobjectdeleteapi.html)|
|PUT Bucket Replication|创建、修改跨区域复制配置|未支持：Account，Role，Owner AccessControlTranslation SourceSelectionCriteria<br>参考：[PUT Bucket Replication](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketPUTreplication.html)|
|GET Bucket Replication|返回设置在Bucket 上的跨区域复制配置|参考：[GET Bucket replication](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketGETreplication.html)|
|Delete Bucket Replication|删除已开启的跨区域复制配置，删除后目标Bucket和objcet依然存在|参考：[Delete Bucket replication](https://docs.aws.amazon.com/zh_cn/AmazonS3/latest/API/RESTBucketDELETEreplication.html)|
