---
title: WDG
published: 2026-08-10
pinned: false
description: WDG（Watchdog）看门狗
tags: [Markdown, Firefly]
category: 硬件
image: ./images/lv1.png
---

# WDG（Watchdog）看门狗
看门狗可监测程序运行状态，由种种原因导致程序卡死或跑飞时，可复位程序以避免其工作异常，保证系统的可靠性与安全性

原理：看门狗本质为定时器，在设定时间内未重置计数器时，WDG硬件电路将自动产生复位信号

STM32看门狗资源：
| 看门狗 |    |
| :--- | :--- |
|独立看门狗(IWDG)|独立工作，只有最晚时间界限|
|窗口看门狗(WWDG)|有精确时间界限范围|

注：窗口看门狗走APB1总线
---