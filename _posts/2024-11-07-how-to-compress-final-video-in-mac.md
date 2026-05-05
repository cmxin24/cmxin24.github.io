---
title: 【教程】MacOS压制Ass硬字幕成片
date: 2024-11-07 20:38:00 +0100
description: 尝试压制组在MacOS上工作的可能

categories: [字幕组, 教程]
tags: [字幕组, 教程, 压制]
---
## 前情提要
   本教程仅讨论如何压制完成了特效制作的最终版ASS文件。

   如何在MacOS上进行特效制作的部分之后可能会另写一篇。

   教程对Windows10及以上版本系统同样适用

## 软件安装
1. 在Mac上执行压制需要用到两个软件：
    - **MKVToolNix**
    - **HandBrake**
    
2. MKVToolNix用于将视频与Ass字幕打包为一个mkv文件，可以在官网 [https://mkvtoolnix.download/macos/](https://mkvtoolnix.download/macos/) 进行下载。截止撰稿日，最新的版本号为88.0。
   
   <center><img src="/assets/img/post/2024-11-07-how-to-compress-final-video-in-mac/mkvtoolnix_download.webp" alt= "mkvtoolnix.download"></center>
    <br/>
   <center><img src="/assets/img/post/2024-11-07-how-to-compress-final-video-in-mac/mkvtoolnix_download2.webp" alt= "mkvtoolnix.download2"></center>
    <br/>
3. 下载后打开dmg文件，将 `MKVToolNix-88.0` 图标拖动到Applications文件夹中，即完成安装。
   
   <center><img src="/assets/img/post/2024-11-07-how-to-compress-final-video-in-mac/mkvtoolnix_install.webp" alt= "mkvtoolnix.install"></center>
   <br/>
4. 同理我们从官网 [https://handbrake.fr/](https://handbrake.fr/) 下载HandBrake的dmg安装包并打开。区别在于这次我们要自己开启 `访达/Finder` 将程序拖动到 `应用程序/Applications` 中。
   
   <center><img src="/assets/img/post/2024-11-07-how-to-compress-final-video-in-mac/handbrake_install.webp" alt= "handbrake.install"></center>
   <br/>
   
5. 之后便可以在系统启动台中找到新安装的两个软件。
   
   <center><img src="/assets/img/post/2024-11-07-how-to-compress-final-video-in-mac/mkvtoolnix_open.webp" alt= "mkvtoolnix.open"></center>
   <br/>

## 生成外挂字幕.mkv档案

1. 开启MKVToolNix，点击 `Add source files` ，将片源和已经制作好的Ass字幕一起添加进去。
   
   <center><img src="/assets/img/post/2024-11-07-how-to-compress-final-video-in-mac/mkvtoolnix_add_files.webp" alt= "mkvtoolnix.add.files"></center>
   <br/>
2. 然后点击 `Start multiplexing` ，将视频与字幕合并。由于不涉及编码，通常瞬间就会完成，并存放在下方的 `Destination file` 路径中。
   
   <center><img src="/assets/img/post/2024-11-07-how-to-compress-final-video-in-mac/mkvtoolnix_start.webp" alt= "mkvtoolnix.strat"></center>
   <br/>
3. 打开生成的文件，检查字幕是否有顺利添加。推荐使用开源播放器 `VLC` 或 `IINA` ，因为系统自带的 `QuickTime Player` 无法打开.mkv文件。
   
   <center><img src="/assets/img/post/2024-11-07-how-to-compress-final-video-in-mac/mkvtoolnix_result.webp" alt= "mkvtoolnix.result"></center>
   <br/>

## 压制硬字幕版本

1. 打开 `HandBrake` ，选择用mkvtoolnix生成的 `.mkv` 文件。
   
    <center><img src="/assets/img/post/2024-11-07-how-to-compress-final-video-in-mac/handbrake_open.webp" alt= "handbrake.open"></center>
   <br/>
2. 此处提供一个json预设，可以直接导入以减少配置负担。参考了[V2EX网友的帖子](https://fast.v2ex.com/t/1060444)，并根据我们组的习惯进行了调整。
   
   点击下载：[1080p_x264_QAF.json](https://github.com/cmxin24/cmxin24.github.io/blob/master/downloads/1080p_16%3A9_x264_QAF.json)
   
   <center><img src="/assets/img/post/2024-11-07-how-to-compress-final-video-in-mac/download_json.webp" alt= "download.json"></center>
   <br/>
   下载后根据如下方式导入：

    <center><img src="/assets/img/post/2024-11-07-how-to-compress-final-video-in-mac/add_new_json.webp" alt= "add.new.json"></center>
   <br/>
   日后再用直接切换即可：

   <center><img src="/assets/img/post/2024-11-07-how-to-compress-final-video-in-mac/add_new_json_2.webp" alt= "add.new.json.2"></center>
   <br/>
3. 套用好预设后，进入 `字幕` 页面，将我们之前放入的字幕轨道设置为 `烧入` ，意思是制作硬字幕。
   
   <center><img src="/assets/img/post/2024-11-07-how-to-compress-final-video-in-mac/burn_in_1.webp" alt= "burn.in"></center>
   <br/>
4. 预设的配置并非一劳永逸的方案，常常要根据片源的情况和具体的电脑配置进行微调。
   
   打开 `视频` 页面，红框部分是我们较常调整的两个参数。

   <center><img src="/assets/img/post/2024-11-07-how-to-compress-final-video-in-mac/video_setting.webp" alt= "video.setting"></center>
   <br/>
   质量选项的 `RF` 是 `固定码率系数（CRF)` 的简写，常用区间为18-24。数值越小，意味着输出视频的质量（码率）越高，视频文件体积也就越大。

   编码选项的 `预设/preset` 代表编码的速度，通常在 `medium` 、 `slow` 、 `slower` 、 `veryslow` 、 `placebo` 之间选择。同字面意思一样，越向右编码速度越慢，画面越清晰；反之速度快但视频更模糊。

   对于短片而言，RF可设置为18、19，预设为veryslow或placebo，因为总编译时间通常也就10~20分钟。长片则需要根据机器性能反复调整找到适合自己机器的组合，例如可以从 `RF 20` 和 `slower` 开始测试。

   以丐版M3 Pro芯片为例，压制一部90分钟的1080p长片，使用 `slower` 大约需要40分钟， `verslow`下大约需要1小时。

   <center><img src="/assets/img/post/2024-11-07-how-to-compress-final-video-in-mac/start_3.webp" alt= "start.3"></center>
   <br/>

   <center><img src="/assets/img/post/2024-11-07-how-to-compress-final-video-in-mac/start_2.webp" alt= "start.2"></center>
   <br/>
5. 最下方可调整输出的文件名以及保存位置。一切就绪后点击顶部的 `开始` 。
   
   <center><img src="/assets/img/post/2024-11-07-how-to-compress-final-video-in-mac/start.webp" alt= "srart"></center>
   <br/>
6. 压制开始后，顶部按钮会变成 `停止` 与 `暂停` 。最下方将预估完成压制所需的时间。
   
   <center><img src="/assets/img/post/2024-11-07-how-to-compress-final-video-in-mac/stop_1.webp" alt= "stop.1"></center>
   <br/>
   如果觉得预估的剩余时间太久难以接受，可以点击 `停止` --> `全部停止` 取消本次编码，然后向左调整 `预设` 的速度。

   <center><img src="/assets/img/post/2024-11-07-how-to-compress-final-video-in-mac/stop_2.webp" alt= "stop.2"></center>
   <br/>
   如果转码完成后的文件体积太大，例如长片超过2G，则向左调整RF数值重新压制。
   <br>
7. 完成后要对压制视频进行检查，包括分辨率是否正确、体积是否合适、有无压制错误产生的黑屏/色块，以及字幕位置与大小是否正常等。在 `QuickTime Player` 中点击窗口， 可打开 `影片检查器` ，查看视频的分辨率、码率等信息。
   
   <center><img src="/assets/img/post/2024-11-07-how-to-compress-final-video-in-mac/info.webp" alt= "info"></center>
   <br/>
   注：本教程使用的视频样例为合作项目，对方要求字幕放在顶部，非字幕组常用模板。

