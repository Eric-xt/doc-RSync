# 使用指南

>Use guide file porject.

### 平台不提供视频播放链接，相关内容均来源于网络。

[返回R-SYNC](http://shixtao.top)
 
 #### 背景：HLS介绍
  
平台支持的视频格式为`.m3u8`和`.mp4`，`MP4`是我们常见的视频格式，往往我们在播放服务器视频时直接就是请求的`MP4`视频源。但其实这样并不好，`MP4`头文件`[ftyp+moov]`较大，
初始化的播放需要下载完整的头文件并进行解析，之后再下载一定长度的可播视频片段才能进行播放。另外随着视频尺寸的增大头文件也会不断变大，这个初始播放时间也会更长。
针对这种情况需要一种能加快视频初始解析的方法，`HLS`就是苹果提出的用于解决这种问题的方案。
`HLS`为`HTTP Live Streaming`的缩写，是由苹果公司提出的基于`HTTP`的流媒体网络传输协议，它可以同时支持**直播**和**点播**，还支持**多清晰度**、**音视频双轨**、**字幕**等功能。
它的原理是将一整条视频分成多段小的视频，完整的播放是由这一个个片段拼接而成的。  
它的大致原理是这样的：  
1. 采集音视频
2. 在服务器编码音视频
3. 编码后以`MPEG-2`的传输串流形式交由切片器`（Stream Segmenter）`
4. 切片器创建索引文件和`ts`播放列表，索引文件用于指示音视频位置，`ts`为真实的多媒体片段
5. 将上一步资源放到`HTTP`服务器上
6. 客户端请求该索引文件进行播放，可以通过索引文件找到播放内容  

实现`HLS`的一个关键步骤是上面的第四步，即索引文件和`ts`播放列表的组织。这里用到的就是`M3U8`格式。
`M3U8`是`Unicode`版本的`M3U`，8代表使用的是`UTF-8`编码，`M3U`和`M3U8`都是多媒体列表的文件格式。`m3u`格式的文件只是存储多媒体播放列表，
提供了一个指向其他位置的音频视频文件的索引，你播放的还是那些被指向的文件，用记事本打开`m3u`文件可以查看所指向文件的地址及文件的属性，以选用合适播放器播放...
[更多详细介绍](http://www.cocoachina.com/articles/900861)
  
以下为网络搜集的一些视频链接：
[github直播源相关资源汇总](https://github.com/ziliudi/ziliudi)

```国内电视台直播源
#EXTINF:-1 ,CCTV-1综合
http://ivi.bupt.edu.cn/hls/cctv1hd.m3u8
#EXTINF:-1 ,CCTV-2财经
http://ivi.bupt.edu.cn/hls/cctv2.m3u8
#EXTINF:-1 ,CCTV-3综艺
http://ivi.bupt.edu.cn/hls/cctv3hd.m3u8
#EXTINF:-1 ,CCTV-4国际
http://ivi.bupt.edu.cn/hls/cctv4.m3u8
#EXTINF:-1 ,CCTV-5体育
http://ivi.bupt.edu.cn/hls/cctv5hd.m3u8
#EXTINF:-1 ,CCTV-6高清
http://ivi.bupt.edu.cn/hls/cctv6hd.m3u8
#EXTINF:-1 ,CCTV-7军事农业
http://ivi.bupt.edu.cn/hls/cctv7.m3u8
#EXTINF:-1 ,CCTV-8高清
http://ivi.bupt.edu.cn/hls/cctv8hd.m3u8
#EXTINF:-1 ,CCTV-9纪录
http://ivi.bupt.edu.cn/hls/cctv9.m3u8
#EXTINF:-1 ,CCTV-10科教
http://ivi.bupt.edu.cn/hls/cctv10.m3u8
#EXTINF:-1 ,CCTV-11戏曲
http://ivi.bupt.edu.cn/hls/cctv11.m3u8
#EXTINF:-1 ,CCTV-12社会与法
http://ivi.bupt.edu.cn/hls/cctv12.m3u8
#EXTINF:-1 ,CCTV-13新闻
http://ivi.bupt.edu.cn/hls/cctv13.m3u8
#EXTINF:-1 ,CCTV-14少儿
http://ivi.bupt.edu.cn/hls/cctv14.m3u8
#EXTINF:-1 ,CCTV-15音乐
http://ivi.bupt.edu.cn/hls/cctv15.m3u8
#EXTINF:-1 ,CCTV-5+体育
http://ivi.bupt.edu.cn/hls/cctv5phd.m3u8
```

