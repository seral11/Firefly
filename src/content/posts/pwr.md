---
title: PWR
published: 2026-08-09
pinned: false
description: PWR（Power Control）电源控制
tags: [Markdown, Firefly]
category: 硬件
image: ./images/lv1.png
---

# 介绍

PWR 控制STM32内部的电源供电，可实现可编程电压检测器(PVD)和低功耗模式，走APB1总线

|  |  |  |
| :--- | :--- | :--- |
|可编程电压检测器|监测VDD电源电压|当VDD不在PVD阈值范围内时，PVD会触发中断，执行中断操作（如紧急关闭等 由程序决定）|
|低功耗模式|睡眠（Sleep） 停机（Stop） 待机（Standby）|当系统处于空闲时可降低功耗（修改主频来实现）|

![alt text](images/image.png)
![alt text](images/image-1.png)
---
<span style="color:blue;">POR</span> 阈值上限    
<span style="color:BLUE;">PDR</span> 阈值下限  
数据参考STM32F10XXX手册5.3.3

## PVD
---
![alt text](images/image-2.png)
---
![alt text](images/image-3.png)
---

## 低功耗模式
---
![alt text](images/image-4.png)
---
### 停止模式
进入并退出后系统将默认选择HSL(8MHz)主频,如有需要应调用SystemInit()重置为HSE(9*8MHz)
