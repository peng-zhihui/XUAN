<h1 align="center">XUAN</h1>
<div align="center">


<i>bicycle into a self-driving car!</i>

<a href="https://github.com/peng-zhihui/XUAN/stargazers"><img src="https://img.shields.io/github/stars/peng-zhihui/XUAN" alt="Stars Badge"/></a>
<a href="https://github.com/peng-zhihui/XUAN/network/members"><img src="https://img.shields.io/github/forks/peng-zhihui/XUAN" alt="Forks Badge"/></a>
<a href="https://github.com/peng-zhihui/XUAN/pulls"><img src="https://img.shields.io/github/issues-pr/peng-zhihui/XUAN" alt="Pull Requests Badge"/></a>
<a href="https://github.com/peng-zhihui/XUAN/issues"><img src="https://img.shields.io/github/issues/peng-zhihui/XUAN" alt="Issues Badge"/></a>
<a href="https://github.com/peng-zhihui/XUAN/graphs/contributors"><img alt="GitHub contributors" src="https://img.shields.io/github/contributors/peng-zhihui/XUAN?color=2b9348"></a>
<a href="https://github.com/peng-zhihui/XUAN/blob/master/LICENSE"><img src="https://img.shields.io/github/license/peng-zhihui/XUAN?color=2b9348" alt="License Badge"/></a>

<a href="https://github.com/peng-zhihui/XUAN"><img src="https://img.shields.io/static/v1?label=&labelColor=505050&message=Chinese 中文自述文件&color=%230076D6&style=flat&logo=google-chrome&logoColor=green" alt="website"/></a>

<a href="https://www.youtube.com/watch?v=kCL2d7wZjU8"><img src="https://img.shields.io/youtube/views/kCL2d7wZjU8?style=social" alt="YouTube Video Views"/></a>
<a href="https://www.youtube.com/channel/UCBAdGeil51Iw4y29Sh9Y7hA"><img src="https://img.shields.io/youtube/channel/subscribers/UCBAdGeil51Iw4y29Sh9Y7hA?style=social" alt="YouTube Channel Subscribers"/></a>
  
<!-- <img src="http://hits.dwyl.com/peng-zhihui/XUAN.svg" alt="Hits Badge"/> -->

<i>Loved the project? Please consider giving a Star ⭐️ to help it improve!</i>

</div>



---


![](2.Structure/xuan.jpg)

> Project video: [[Self-made] I made the bicycle into a self-driving car! ! [Hardcore]](https://www.bilibili.com/video/BV1fV411x72a)

## file description

Inside `Hardware` is the PCB file of the controller, including the reference scheme of the carrier board of the Ascend A200 module. The MCU is based on ESP32, equipped with MPU6050, and connected to the driver through the CAN bus.

`Structure` contains the body structure design file. The step is exported by Fusion. There may be some bugs. It is recommended to directly download the Fusion360 project and open it in the software: https://a360.co/2TOtZRd

The software part has not been released for the time being because the coupling of the FOC driver is not universal, but I will open source a mini simplified version of the bicycle complete solution (using a small DC motor) including the source code later, you can wait for a while.

In addition, I am sorting out a robot embedded development framework (REF), which will abstract some tools and development modes commonly used in robot development, and will also update a warehouse separately at that time.
