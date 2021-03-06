# 对象存储

> Use object storage to get video url.

什么是对象存储？[对象存储](https://baike.baidu.com/item/%E5%AF%B9%E8%B1%A1%E5%AD%98%E5%82%A8/6888656)，也叫做基于对象的存储，是用来描述解决和处理离散单元的方法的通用术语，这些离散单元被称作为对象。
就像文件一样，对象包含数据，但是和文件不同的是，对象在一个层结构中不会再有层级结构。每个对象都在一个被称作存储池的扁平地址空间的同一级别里，一个对象不会属于另一个对象的下一级。
文件和对象都有与它们所包含的数据相关的元数据，但是对象是以扩展元数据为特征的。每个对象都被分配一个唯一的标识符，允许一个服务器或者最终用户来检索对象，而不必知道数据的物理地址。
这种方法对于在云计算环境中自动化和简化数据存储有帮助。  

**通俗来讲，`对象存储`用来将一些文件上传至云空间，可以通过链接直接在浏览器访问。**  

如果你购买了云存储服务，那真是再好不过了，这将为我们提供了额外的技术支持。我们以[七牛云](https://www.qiniu.com/)为例，首先注册一个七牛云账号，登陆后点击右上角进入控制台界面，选择`立即添加对象存储`  
  
![](https://img.imgdb.cn/item/606d50238322e6675cbc944c.jpg)  
  
为空间去取一个自定义名字，因为国内访问速度最快，存储区域选择**华东**，**华北**，**华南**其中一个，然后访问控制选择`公开`，点击`确定`。空间创建好后，点击空间名进入管理界面，可以看到相关信息:   
  
![](https://img.imgdb.cn/item/606d51828322e6675cbdeebb.jpg)  
  
默认会分配一个时限为30天的测试域名，点击`文件管理`，上传视频文件，如果是第一次使用，建议直接点击`选择文件`上传即可，无需更改存储类型等设置。上传成功后点击`返回`按钮返回上一页，
可以看到已上传了一个视频文件，点击`更多`按钮，复制视频链接，即可直接食用。  
  
![](https://img.imgdb.cn/item/606d52d78322e6675cbf68fb.jpg)