---
title: spi
published: 2026-08-03
pinned: false
description: spi协议
tags: [Markdown, Firefly]
category: 硬件
image: ./images/
---


# SPI
<span style="color:#61AFEF;">SPI（Serial Peripheral Interface）</span>是由Motorola公司开发的一种通用数据总线

工作模式/特点：<span style="color:#61AFEF;">同步 全双工 一主多从</span> 

|名词|含义|别名|
| :--- | :--- | :--- |
|SS|从机选择|CS（片选）|
|SCK|串行时钟线|CLK,SLK|
|MOSI|主机输出 从机输入|DI（从机）|
|MISO|主机输入 从机输出|DO（从机）|

SPI协议规定：所有硬件设备的<span style="color:#61AFEF;">SCK MOSI MISO</span>应当分别连接在一起；主机需引出多条<span style="color:#61AFEF;">SS</span>控制线分别与从机的<span style="color:#61AFEF;">SS</span>引脚相连接。
![alt text](image-6.png)
## 时序
![alt text](image-7.png)


