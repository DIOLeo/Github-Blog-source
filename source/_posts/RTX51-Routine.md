---
layout: "post"
title: "RTX51 Tiny"
subtitle: "基础例程"
description: "RTX51 Tiny Routine"
date: 2018-11-26 07:11:47
author: DIO
catalog: true
header-img: "RTX51-RoutineBg.jpg"
tags: 
    - Embedd
---

学习 `RTX51` 顺手而作,缓慢更新,在此留备份,以后慢慢做更多(如果有时间的话)  
板子是 `STC89C51` 的MCU,国内普中开发板,很容易买到也是很普遍的版本  

<!-- more -->

***
# Overview 摘要  

给所有正在学或者想要学习 `RTX51 Tiny` 的朋友提供一些自己写的程序 仅供参考  
您有什么好的意见或者建议欢迎指出 联系方式 diodev@outlook.com  
如果没有接触过RTX51的朋友建议先阅读官方手册 https://github.com/DIOLeo/RTX51-Tiny-ChineseDoc  

# Contents 目录  

2017.12.09 `跑马灯` LED light display  
https://github.com/DIOLeo/RTX51_routine/tree/master/20171209_rtx51LED  

2017.12.13 `DS1302时钟模块 + LCD1602液晶显示时间` DS1302+LCD1602  
https://github.com/DIOLeo/RTX51_routine/tree/master/20171212_rtx51ds1302  

# Tool Requirements 编译环境要求  

本人使用的编译环境如下  
IDE-Version: μVision V5.20.0.39  
Toolchain: PK51 Prof. Developers Kit Version: 9.56.0.0  
C Compiler: C51.exe V9.56.0.0  
Assembler: A51.exe V8.2.5.0  
Linker/Locator: BL51.exe V6.22  
Library Manager: LIB51.exe V4.30.1.0  
Hex Converter: OH51.exe V2.7.0.0  
CPU DLL: S8051.DLL V3.106.0.0  
Dialog DLL: DP51.DLL V2.63.0.0  
