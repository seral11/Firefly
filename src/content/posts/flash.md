---
title: FLASH
published: 2026-08-14
pinned: false
description: FLASH闪存
tags: [Markdown, Firefly]
category: 硬件
image: ./images/lv1.png
---

# FLASH闪存
STM32F1系列的FLASH包含：<span style="color:#61AFEF;"><span title="主存储器">程序存储器</span> 系统存储器 选项字节</span>
通过外设<span style="color:#61AFEF;">闪存存储器接口</span>可以对程序存储器和选项字节进行擦除和编程

常用于：利用程序存储器的剩余空间来保存掉电不丢失的用户数据
       通过在程序中编程（IAP），实现程序的自我更新
![alt text](images/6.png)
