---
title: FLASH.h
published: 2026-08-14
pinned: false
description: FLASH闪存
tags: [Markdown, Firefly]
category: STM32标准库
image: ./images/lv1.png
---
```c powershell title="FLASH_Status"
typedef enum
{
    FLASH_BUSY = 1,      // Flash 忙，BSY 位为 1
    FLASH_ERROR_PG,      // 编程错误（PGERR 置位）
    FLASH_ERROR_WRP,     // 写保护错误（WRPRTERR 置位）
    FLASH_COMPLETE,      // 操作成功完成
    FLASH_TIMEOUT        // 等待超时（如等待 BSY 清零超时）
} FLASH_Status;
```
| 库函数 | return | 功能 |
| :--- | :--- | :--- |
|FLASH_Unlock( void )|`void`|解锁FPEC|
|FLASH_Lock( void )|`void`|上锁FPEC|
|FLASH_ErasePage( uint32_t DATA )|`FLASH_Status`|指定地址页擦除|
|FLASH_EraseAllPages( void )|`void`|全擦除|



