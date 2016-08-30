#简介
快网FastMedia Player提供基于智能FastMedia调度系统的高效可靠的传输、转码、分发的一站式直播点播服务平台，目前支持Http＋Flv的流媒体直播。提供播放器SDK，具有低延迟、高安全、高并发、易接入、多终端、控制接口多、统计信息详细等特点;
##亮点介绍
    1 具有低延迟、低卡顿、播放流畅的特点。
    2 平台适应性：android、iOS、PC  
    3 播放场景定制功能  
      3.1 支持首帧渲染  
      3.2 支持缓存功能
      3.3 后台中断播放  
    4 播放卡顿智能调整功能
      4.1 支持卡顿暂停
      4.2 支持最大卡顿时间设置
      4.3 支持卡顿信息统计功能
    5 网络监控
      5.1 支持超时时间设置
      5.2 支持重连次数设置
      5.3 实时监控网络状态
    6 灵活的播放视图层
      6.1 提供一站式播放控制器快速集成
      6.2 提供灵活的播放界面，可以灵活实现画中画等各种特效
    7 其它特点
      7.1 支持静音，音量百分比调节功能
      7.2 提供大量播放状态统计信息
##FastMediaPlayer SDK（PC端flash版本）概述

	低延时直播体验，配合快网FastMedia调度系统，可以享受视频加速服务。
	灵活自定义的屏幕界面。
	支持Http＋flv及RTMP。
	几十K大小的超轻量级直播sdk。



###Player API Overview
| @function                                | @abstract                                |      @param      |
| ---------------------------------------- | :--------------------------------------- | :--------------: |
| -playVideo():void                        | Begin to play of the current item        |        --        |
| -stop():void                             | Stop playing                             |        --        |
| -setPlayerUrl(url:String):void           | Set player play address                  |   play address   |
| -setPlayerViewScale(w_scale:Number, h_scale:Number):void | Set player screen zoom scale             | zoom scale,0-1.0 |
| -setMediaCacheTime(buftime:Number):void  | Set the media data cache time            |  cache time(ms)  |
| -setPlayerVolume(volumn:Number):void     | Set player volume                        |  volume(0-1.0)   |
| -setConnectTimeout(time:Number):void     | Set timeout with server connection       |     time(ms)     |
| -setReconnectTimes(times:int):void       | Set the number of times to reconnect to the server |      times       |
| -setFirstMaxPlayTime(maxFirstPlayTime:Number):void | If the player does not play in the first maximum time, then the player will reload the play address in any case. |      times       |
| -setMaxStuckTime(maxStuckTime:Number):void | If stuck total time than the maximum stuck time, the player will be re-loaded play address. |     time(ms)     |
| -mute():void                             | Mute playing.                            |        --        |
| -unmute():void                           | Cancel the mute.                         |        --        |



## FastMediaPlayer SDK API 详解

-playVideo():void

​	播放参数设置并播放视频。

-stop():void

​	停止视频播放。



-setPlayerUrl():void

​	设置播放视频的URL地址。

-setPlayerViewScale(w_scale:Number,h_scale:Number):void

​	设置播放器视图缩放比例（目前只是视频区，背景没有一起缩放，后面可能会开放一个接口，让二者可以一起缩放）。

-setMediaCacheTime(buftime:Number):void

​	设置视频播放的缓存时间。

-setPlayerVolumn(volumn:Number):void

​	设置播放视频时的音量大小（0~1）。

-setConnectTimeout(countTimeout:Number):void

​	设置超时时间（单位：ms）。

-setReconnectTimes(recountTimes:int):void

​	设置重连次数（包括超时重连次数和最大起播重连次数）。

-setMaxStuckTime(maxStuckTime:Number):void

​	设置最大卡顿总时长（单位：ms）。

-setFirstMaxPlayTime(firstMaxPlayTime:Number):void

​	设置最大起播时间（单位：ms）。

-mute():void

​	静音。

-unMute():void

​	从静音中恢复（恢复时的音量为静音时的音量）。

-setControllerHidden(hiddenFlag:Boolean):void

​	设置播放控制条的可见性（hiddenFlag为true时，不可见;如果需要在初始化时隐藏，需要通过flashvars来实现，参见DEMO页）。



-getDroppedFrames():int

​	获得当前视频播放的丢帧数。

-getFplayTime():Number

​	获得首帧时间（单位：S）。

-getFTCPpackageT():Number

​	获得第一个TCP包的时间（单位：S）。

-getStuckTimes():int

​	获得卡顿次数。

-getStuckDurationTotal():Number

​	获得卡顿总时长（单位：S）。

-getStuckRate():Number

​	获得视频播放的卡顿率。

-getCurrentPlayTime():String

​	获得当前播放时间。

-getCurrentFPS():int

​	获得当前FPS（frames per second）。

-getBufferLength():Number

​	获得视频播放时的实时buffer长度。

-getRealTimeRate():String

​	获得实时的网络消耗速率（KB/S）。

-getRecountInfo():String

​	获得起播重连信息。

-getTimeoutInfo():String

​	获得延时重连信息。
