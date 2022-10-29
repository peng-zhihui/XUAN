<h1 align="center">XUAN-Bike</h1>
<div align="center">


<a href="https://github.com/peng-zhihui/XUAN/stargazers"><img src="https://img.shields.io/github/stars/peng-zhihui/XUAN" alt="Stars Badge"/></a>
<a href="https://github.com/peng-zhihui/XUAN/network/members"><img src="https://img.shields.io/github/forks/peng-zhihui/XUAN" alt="Forks Badge"/></a>
<a href="https://github.com/peng-zhihui/XUAN/pulls"><img src="https://img.shields.io/github/issues-pr/peng-zhihui/XUAN" alt="Pull Requests Badge"/></a>
<a href="https://github.com/peng-zhihui/XUAN/issues"><img src="https://img.shields.io/github/issues/peng-zhihui/XUAN" alt="Issues Badge"/></a>
<a href="https://github.com/peng-zhihui/XUAN/graphs/contributors"><img alt="GitHub contributors" src="https://img.shields.io/github/contributors/peng-zhihui/XUAN?color=2b9348"></a>
<a href="https://github.com/peng-zhihui/XUAN/blob/master/LICENSE"><img src="https://img.shields.io/github/license/peng-zhihui/XUAN?color=2b9348" alt="License Badge"/></a>

<a href="https://github.com/peng-zhihui/XUAN/blob/main/enREADME.md"><img src="https://img.shields.io/static/v1?label=&labelColor=505050&message=English README 英文自述文件&color=%230076D6&style=flat&logo=google-chrome&logoColor=green" alt="website"/></a>

<a href="https://www.youtube.com/watch?v=FmKTiH5Lca4"><img src="https://img.shields.io/youtube/views/FmKTiH5Lca4?style=social" alt="YouTube Video Views"/></a>
<a href="https://www.youtube.com/channel/UCBAdGeil51Iw4y29Sh9Y7hA"><img src="https://img.shields.io/youtube/channel/subscribers/UCBAdGeil51Iw4y29Sh9Y7hA?style=social" alt="YouTube Channel Subscribers"/></a>
  
<!-- <img src="http://hits.dwyl.com/peng-zhihui/XUAN.svg" alt="Hits Badge"/> -->

<i>喜欢这个项目吗？请考虑给 Star ⭐️ 以帮助改进！</i>

</div>

---

![](2.Structure/xuan.jpg)

> 项目视频：[【自制】我把自行车做成了 自 动 驾 驶 ！！【硬核】](https://www.bilibili.com/video/BV1fV411x72a)

## 文件说明

`Hardware`里面是控制器的PCB文件，包括**昇腾A200模组**载板的参考方案。MCU基于ESP32，搭载MPU6050，通过CAN总线连接驱动器。

`Structure`里面是车身结构设计文件，step是Fusion导出的可能有些BUG，建议直接下载这个Fusion360的工程在软件里打开：https://a360.co/2TOtZRd

软件部分由于涉及到FOC驱动器的耦合并不是通用的所以暂时未放出，不过我后面会开源一个包括源码的迷你简化版的自行车完整方案（使用小型直流电机），大家可以等待一阵子。

另外，我正在整理一个机器人嵌入式开发框架（REF），会统一抽象出机器人开发中常用的一些工具和开发模式，到时候也会单独更新一个仓库。

