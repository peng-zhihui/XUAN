[[_TOC_]]

## 0. 前言

> 本篇文章用于记录学习昇腾ATLAS 200DK使用过程中遇到的一些问题和使用说明，我是自己设计了新款载板，大家如果要尝试的话可以直接购买官方的200DK盒子。

![image-20210207154325217](/.assets/home/image-20210207154325217.png)

### 关于ATLAS 200DK

Atlas 200 DK 开发者套件（型号 3000）是以`Atlas-200 AI加速模块`为核心的开发者板形态的终端类产品，主要功能是将`Atlas-200 AI加速模块`的接口对外开放，做成底板+核心板的模式，方便用户快速简捷地使用。

**特性方面：**

* 可提供22TOPS（INT8）的峰值计算能力
* 支持两路Camera输入，两路ISP图像处理，支持HDR10高动态范围技术标准
* 支持1000M以太网对外提供高速网络连接，匹配强劲计算能力
* 通用的40-pin扩展接口（预留），方便产品原型设计

**系统架构图如下：**

![image-20210207154341771](/.assets/home/image-20210207154341771.png)

> 值得注意的是，200DK开发板上板载了一个Hi3559C的处理器，用于对接CSI摄像头（因为ATLAS-200模块不带相关接口），与ATLAS-200模块通过PCIE连接。而我们开发时其实是用不到Hi3559C的（其上面的操作系统也没有起来），所有操作都是在ATLAS-200上的Ubuntu系统进行。

## 1. ATLAS 200DK 相关资源链接

* **【200DK开发板】的在线文档**：https://support.huaweicloud.com/A200dk_3000_c75/index.html
* **【200模块】的在线文档**：https://support.huawei.com/enterprise/zh/ascend-computing/a200-3000-pid-250702933
* **在线教程：**[华为云学院](https://education.huaweicloud.com/courses/course-v1:HuaweiX+CBUCNXA001+Self-paced/about?isAuth=0&cfrom=hwc)

> 在公司内部的iLearning平台也有大量优秀视频课程：[iLearning](http://ilearning.huawei.com/edx/next/portal/programs/shengteng/)