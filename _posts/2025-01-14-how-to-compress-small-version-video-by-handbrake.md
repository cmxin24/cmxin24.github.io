---
title: 【教程】MacOS压制视频小版本
date: 2025-01-14 13:00:00 +0100
description: 简单介绍Mac系统压制小版本的方法

categories: [字幕组, 教程]
tags: [字幕组, 教程, 小版本, HandBrake]
---

> 本教程对Windows10及以上版本系统同样适用

## 软件安装

1. 从官网 [https://handbrake.fr/](https://handbrake.fr/) 下载HandBrake的dmg安装包并打开。
   <center><img src="/assets/img/post/2025-01-14-how-to-compress-small-version-video-by-handbrake/download.webp" alt= "handbrake.download"></center>
   <br/>

2. 开启 `访达/Finder` 将程序拖动到 `应用程序/Applications` 中。
   <center><img src="/assets/img/post/2025-01-14-how-to-compress-small-version-video-by-handbrake/install.webp" alt= "handbrake.install"></center>
   <br/>
   
## 加载预设

1. 开启程序，选择你需要压制的影片。
   <center><img src="/assets/img/post/2025-01-14-how-to-compress-small-version-video-by-handbrake/open.webp" alt= "handbrake.open"></center>
   <br/>

2. 点击下载预设：[540p 16/9 小版本 QAF.json](https://github.com/cmxin24/cmxin24.github.io/blob/master/downloads/540p_16%3A9_%E5%B0%8F%E7%89%88%E6%9C%AC_QAF.json)

   <center><img src="/assets/img/post/2025-01-14-how-to-compress-small-version-video-by-handbrake/download_preset.webp" alt= "download.preset"></center>
   <br/>

3. 如图所示，在主界面中导入小版本预设。
   <center><img src="/assets/img/post/2025-01-14-how-to-compress-small-version-video-by-handbrake/preset.webp" alt= "handbrake.preset"></center>
   <br/>
   
4. 点击预设名称进行切换。
   <center><img src="/assets/img/post/2025-01-14-how-to-compress-small-version-video-by-handbrake/switch.webp" alt= "handbrake.540p"></center>
   <br/>

5. 这里讲解一下预设里做出调整的部分，理解原理后也可以自己调配方。
   
   在 `尺寸` 页面，将 `分辨率` 设置为960*540，不用担心影片的宽高比不同，打开 `最佳大小` 后会自动缩放。
   <center><img src="/assets/img/post/2025-01-14-how-to-compress-small-version-video-by-handbrake/size.webp" alt= "handbrake.size"></center>
   <br/>
   
   下方的 `自动` 代表着，如果影片有黑白，最终的压制版本会把黑白裁切掉，所以如果最后生成的影片分辨率很怪就说明被去黑边了。
   <br/>

6. 切换到 `视频` 页面，主要的调节选项是质量和编码。
   <center><img src="/assets/img/post/2025-01-14-how-to-compress-small-version-video-by-handbrake/video.webp" alt= "handbrake.video"></center>
   <br/>

   质量选项的 `RF` 是 `固定码率系数（CRF)` 的简写，常用区间为18-24。数值越小，意味着输出视频的质量（码率）越高，视频文件体积也就越大。压制小版本通常22-24都可以。

   编码选项的 `预设/preset` 代表编码的速度，通常在 `medium` 、 `slow` 、 `slower` 、 `veryslow` 、 `placebo` 之间选择。同字面意思一样，越向右编码速度越慢，画面越清晰；反之速度快但视频更模糊。小版本对画质要求不高，所以 `fast` 就可以了。

## 小版本压制

1. 最下方可调整输出的文件名以及保存位置。一切就绪后点击顶部的 `开始` 。压制开始后，顶部按钮会变成 `停止` 与 `暂停` 。最下方将预估完成压制所需的时间。
   
   <center><img src="/assets/img/post/2025-01-14-how-to-compress-small-version-video-by-handbrake/start.webp" alt= "start"></center>
   <br/>

2. 压制完成后请检查视频大小是否成功减少，以及能否正常播放，简单拖动进度条确保没有因为压制异常产生的黑屏或色块。
   
   <center><img src="/assets/img/post/2025-01-14-how-to-compress-small-version-video-by-handbrake/file.webp" alt="file"></center>
   <br/>
   
   

