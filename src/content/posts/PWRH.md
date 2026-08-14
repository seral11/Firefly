---
title: PWR.h
published: 2026-08-09
pinned: false
description: PWR（Power Control）电源控制标准库
tags: [Markdown, Firefly]
category: STM32标准库
image: ./images/lv1.png
---

| 库函数 | return | 功能 |
| :--- | :--- | :--- |
| PWR_DeInit(void)|`void`|恢复缺省配置|
| PWR_BackupAccessCmd(FunctionalState NewState)|void`|使能后备区域访问|
| PWR_PVDCmd(FunctionalState NewState)|`void`|使能PVD|
| PWR_PVDLevelConfig(uint32_t PWR_PVDLevel)|`void`|配置PVD电压|
| PWR_WakeUpPinCmd(FunctionalState NewState)|`void`|使能WKUP引脚|
| PWR_EnterSTOPMode(uint32_t PWR_Regulator, uint8_t PWR_STOPEntry)|`void`|进入停止模式|
| PWR_EnterSTANDBYMode(void)|`void`|进入待机模式|
| PWR_GetFlagStatus(uint32_t PWR_FLAG)|`FlagStatus`|获取标志位|
| PWR_ClearFlag(uint32_t PWR_FLAG)|`void`|清除标志位|


