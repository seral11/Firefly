---
title: bkp
published: 2026-08-03
pinned: false
description: bkp备份寄存器[APB1总线]
tags: [Markdown, Firefly]
category: 硬件
image: ./images/lv1.png
---


## BKP备份寄存器

BKP可用于存储 用户（应用）数据。当VDD(系统电源2.0~3.6v)切断时，由VBAT(备用电池电源1.8~3.6v)供电，系统复位和电源复位均不会造成影响。


1.TAMPER引脚的侵入事件将所有备份寄存器数据清除

2.RTC引脚可输出RTC校准时钟，RTC闹钟脉冲或者秒脉冲


设计上 用户数据存储容量：20B(中容量 小容量) 84B(大容量 互联型)

### 基本结构


