---
layout: "post"
title: "Windows 10 实用工具"
subtitle: "持续更新"
description: "Windows 10 Tools"
date: 2018-12-24 21:54:35
author: DIO
catalog: true
header-img: "Windows-Tool.jpg"
tags: 
    - Windows
    - Software
---

做系统是常事,捣鼓系统设置也是常事,随着时间流淌积累了越来越多的实用工具  
有的是网上找的,有的是自己写的,在此做一个集中整理  
本文会对注册表进行大量修改,数据无价,请务必备份  
持续更新,敬请关注.  

***  

# 更改系统字体 微软雅黑 为 宋体  

> **请注意,此注册表会导致 微软雅黑 字体无法使用!**  

1. 新建文本文档  
2. 将下列代码粘贴并保存  
3. 更改文件名后缀为 `reg`  
4. 双击添加注册表  

```dos
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Fonts]
"Microsoft YaHei & Microsoft YaHei UI (TrueType)"="simsun.ttc"
"Microsoft YaHei Bold & Microsoft YaHei UI Bold (TrueType)"="simsun.ttc"
"Microsoft YaHei Light & Microsoft YaHei UI Light (TrueType)"="simsun.ttc"

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\FontSubstitutes]
"Microsoft YaHei"="SimSun"
"Microsoft YaHei UI"="SimSun"  
```

***  

# 更改系统窗口 滚动条 标题栏 宽度  

1. 新建文本文档  
2. 将下列代码粘贴并保存  
3. 更改文件名后缀为 `reg`  
4. 双击添加注册表  

```dos
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\Control Panel\Desktop\WindowMetrics]
"BorderWidth"="0"
"CaptionFont"=hex:f4,ff,ff,ff,00,00,00,00,00,00,00,00,00,00,00,00,90,01,00,00,\
  00,00,00,01,00,00,05,00,4d,00,69,00,63,00,72,00,6f,00,73,00,6f,00,66,00,74,\
  00,20,00,59,00,61,00,48,00,65,00,69,00,20,00,55,00,49,00,00,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00
"CaptionHeight"="-270"
"CaptionWidth"="-270"
"IconFont"=hex:f4,ff,ff,ff,00,00,00,00,00,00,00,00,00,00,00,00,90,01,00,00,00,\
  00,00,01,00,00,05,00,4d,00,69,00,63,00,72,00,6f,00,73,00,6f,00,66,00,74,00,\
  20,00,59,00,61,00,48,00,65,00,69,00,20,00,55,00,49,00,00,00,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00
"IconTitleWrap"="1"
"MenuFont"=hex:f4,ff,ff,ff,00,00,00,00,00,00,00,00,00,00,00,00,90,01,00,00,00,\
  00,00,01,00,00,05,00,4d,00,69,00,63,00,72,00,6f,00,73,00,6f,00,66,00,74,00,\
  20,00,59,00,61,00,48,00,65,00,69,00,20,00,55,00,49,00,00,00,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00
"MenuHeight"="-285"
"MenuWidth"="-285"
"MessageFont"=hex:f4,ff,ff,ff,00,00,00,00,00,00,00,00,00,00,00,00,90,01,00,00,\
  00,00,00,01,00,00,05,00,4d,00,69,00,63,00,72,00,6f,00,73,00,6f,00,66,00,74,\
  00,20,00,59,00,61,00,48,00,65,00,69,00,20,00,55,00,49,00,00,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00
"ScrollHeight"="-165"
"ScrollWidth"="-165"
"Shell Icon Size"="32"
"SmCaptionFont"=hex:f4,ff,ff,ff,00,00,00,00,00,00,00,00,00,00,00,00,90,01,00,\
  00,00,00,00,01,00,00,05,00,4d,00,69,00,63,00,72,00,6f,00,73,00,6f,00,66,00,\
  74,00,20,00,59,00,61,00,48,00,65,00,69,00,20,00,55,00,49,00,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00
"SmCaptionHeight"="-330"
"SmCaptionWidth"="-330"
"StatusFont"=hex:f4,ff,ff,ff,00,00,00,00,00,00,00,00,00,00,00,00,90,01,00,00,\
  00,00,00,01,00,00,05,00,4d,00,69,00,63,00,72,00,6f,00,73,00,6f,00,66,00,74,\
  00,20,00,59,00,61,00,48,00,65,00,69,00,20,00,55,00,49,00,00,00,00,00,00,00,\
  00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00,00
"PaddedBorderWidth"="0"
"AppliedDPI"=dword:00000060
"IconSpacing"="-1125"
"IconVerticalSpacing"="-1125"
"MinAnimate"="0"  
```

***  

# 隐藏 Windows10 锁屏界面网络和关机按钮  

1. 新建文本文档  
2. 将下列代码粘贴并保存  
3. 更改文件名后缀为 `reg`  
4. 双击添加注册表  

```dos
Windows Registry Editor Version 5.00
[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\System]
"DontDisplayNetworkSelectionUI"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System]
"shutdownwithoutlogon"=dword:00000000  
```

***  

# Windows10 家庭版开启组策略  

1. 新建文本文档  
2. 将下列代码粘贴并保存  
3. 更改文件名后缀为 `bat`  
4. 双击运行批处理  

```dos
@echo off
pushd "%~dp0"
dir /b C:\Windows\servicing\Packages\Microsoft-Windows-GroupPolicy-ClientExtensions-Package~3*.mum >List.txt
dir /b C:\Windows\servicing\Packages\Microsoft-Windows-GroupPolicy-ClientTools-Package~3*.mum >>List.txt
for /f %%i in ('findstr /i . List.txt 2^>nul') do dism /online /norestart /add-package:"C:\Windows\servicing\Packages\%%i"
pause  
```

***  

# Windows10 删除 Onedrive  

1. 新建文本文档  
2. 将下列代码粘贴并保存  
3. 更改文件名后缀为 `bat`  
4. 双击运行批处理  

```dos
@ECHO OFF
%SystemRoot%\SysWOW64\OneDriveSetup.exe /uninstall
RD "%UserProfile%\OneDrive" /Q /S
RD "%LocalAppData%\Microsoft\OneDrive" /Q /S
RD "%ProgramData%\Microsoft OneDrive" /Q /S
RD "C:\OneDriveTemp" /Q /S
REG Delete "HKEY_CLASSES_ROOT\CLSID\{018D5C66-4533-4307-9B53-224DE2ED1FE6}" /f
REG Delete "HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{018D5C66-4533-4307-9B53-224DE2ED1FE6}" /f
END  
```

***  

# 一键配置 JDK 环境变量  

1. 新建文本文档  
2. 将下列代码粘贴并保存  
3. 更改文件名后缀为 `bat`  
4. 双击运行批处理,按提示操作即可  

```dos
@echo off
echo ************************************************************  
echo *                                                          *  
echo *        JDK 系统环境变量设置,请用管理员身份运行           *  
echo *                                                          *  
echo ************************************************************  
echo.    
:START
set /p javahome=请输入JDK安装路径：
IF EXIST "%javahome%\bin\java.exe" GOTO INSTALL
:WARNING
rem 输入目录错误，提示重新输入
echo 您所输入的路径不是JDK安装路径
echo 请重新输入正确的JDK安装路径
pause
goto START
:INSTALL
rem 如输入正确的 JavaSDK 安装目录，开始设置环境变量
echo 输入的路径是:%javahome%
rem LPY  
echo.  
echo === 准备设置环境变量: JAVA_HOME=%javahome%  
echo === 注意: 如果JAVA_HOME存在,会被覆盖,此操作不可逆的,请仔细检查确认!! ===  
echo.  
echo === 准备设置环境变量(后面有个.): CLASSPATH=.;%%JAVA_HOME%%\lib\dt.jar;%%JAVA_HOME%%\lib\tools.jar;  
echo === 注意: 如果CLASSPATH存在,会被覆盖,此操作不可逆的,请仔细检查确认!! ===  
echo.  
echo === 准备设置环境变量: PATH=%%JAVA_HOME%%\bin;%%JAVA_HOME%%\jre\bin;  
echo === 注意: PATH会追加在最前面,  
echo.  
set /P EN=请确认后按 回车键 开始设置!  
echo.  
echo.  
echo.  
echo.  
echo === 新创建环境变量 JAVA_HOME=%javahome%  
setx "JAVA_HOME" "%javahome%" -M  
echo.  
echo.  
echo === 新创建环境变量 CLASSPATH=.;%%JAVA_HOME%%\lib\dt.jar;%%JAVA_HOME%%\lib\tools.jar;  
setx "CLASSPATH" ".;%%JAVA_HOME%%\lib\dt.jar;%%JAVA_HOME%%\lib\tools.jar;" -M  
echo.  
echo.  
echo === 新追加环境变量(追加到最前面) PATH=%%JAVA_HOME%%\bin;%%JAVA_HOME%%\jre\bin;   

wmic ENVIRONMENT where "name='path' and username='<system>'" set VariableValue="%%JAVA_HOME%%\bin;%%JAVA_HOME%%\jre\bin;%path%"
setx path "%path%"
echo.  
echo.   
echo === 请按任意键退出!   
pause>nul  
```

***  

# 一键添加系统环境变量  

1. 新建文本文档  
2. 将下列代码粘贴并保存  
3. 更改文件名后缀为 `bat`  
4. 双击运行批处理,按提示操作即可(**可重复添加**)  

```dos
@echo off
echo ************************************************************  
echo *                                                          *  
echo *          系统环境变量设置,请用管理员身份运行             *  
echo *                                                          *  
echo ************************************************************  
echo.
echo D:\GitHubDesktop\app-1.5.0\resources\app\git\cmd\
echo.
echo D:\NodeJS\
echo.
echo D:\NodeJS\node-global\
echo.
set UserPath=
:START
set /p UserPathTemp=请输入路径:
set UserPath=%UserPath%%UserPathTemp%;
echo 输入的路径是:%UserPath%

:INPUT
set /p Input=是否继续?(回车 = Yes,N = No)

if "%Input%"=="" goto START
if "%Input%"=="N" goto INSTALL
goto INPUT

:INSTALL
echo.  
echo 准备设置环境变量: PATH=%UserPath%
echo PATH会追加在最前面
echo.  
set /P EN=请确认后按 回车键 开始设置!

wmic ENVIRONMENT where "name='path' and UserName='<system>'" set VariableValue="%UserPath%%path%"

:EXIT
exit  
```

***  

# 鼠标方案配置文件  

1. 在鼠标指针 `根目录` 新建文本文档  
2. 将下列代码粘贴
3. 按下列代码注释更改为相应字段  
4. 更改文件名后缀为 `inf`  
5. 右键 `安装`  
6. 控制面板鼠标方案中即可看到效果  

```
[Version]
signature="$CHICAGO$"

[DefaultInstall]
CopyFiles = Scheme.Cur, 
AddReg    = Scheme.Reg

[DestinationDirs]
Scheme.Cur = 10,"%CUR_DIR%"
Scheme.Txt = 10,"%CUR_DIR%"

[Scheme.Reg]
HKCU,"Control Panel\Cursors\Schemes","%SCHEME_NAME%",,"%10%\%CUR_DIR%\%pointer%,%10%\%CUR_DIR%\%help%,%10%\%CUR_DIR%\%work%,%10%\%CUR_DIR%\%busy%,%10%\%CUR_DIR%\%Cross%,%10%\%CUR_DIR%\%Text%,%10%\%CUR_DIR%\%Hand%,%10%\%CUR_DIR%\%Unavailiable%,%10%\%CUR_DIR%\%Vert%,%10%\%CUR_DIR%\%Horz%,%10%\%CUR_DIR%\%Dgn1%,%10%\%CUR_DIR%\%Dgn2%,%10%\%CUR_DIR%\%move%,%10%\%CUR_DIR%\%alternate%,%10%\%CUR_DIR%\%link%"

; -- Common Information

;下列字段改为文件夹下相应文件名
[Scheme.Cur]
 "[MD] [mini] Normal Select v4.0-static.cur"
 "[MD] [mini] Help Select v4.0.ani"
 "[MD] [mini] Working In Background v4.0.ani"
 "[MD] [mini] Busy v4.0.ani"
 "[MD] [mini] Precision Select v4.0.ani"
 "[MD] [mini] Text Select v4.0.ani"
 "[MD] [mini] Handwriting v4.0.ani"
 "[MD] [mini] Unavailable v4.0.ani"
 "[MD] [mini] Vertical Resize v4.0.ani"
 "[MD] [mini] Horizontal Resize v4.0.ani"
 "[MD] [mini] Diagonal Resize 1 v4.0.ani"
 "[MD] [mini] Diagonal Resize 2 v4.0.ani"
 "[MD] [mini] Move v4.0.ani"
 "[MD] [mini] Alternate Select v4.0.ani"
 "[MD] [mini] Link Select v4.0-static.cur"

;按照变量名称改为对应的指针文件的文件名
;CUR_DIR 为 "Cursors\文件夹名(随意起)"
;SCHEME_NAME "方案名称(随意起)"
[Strings]
CUR_DIR		= "Cursors\SmallBlack"
SCHEME_NAME     = "SmallBlack"
pointer		= "[MD] [mini] Normal Select v4.0-static.cur"
help		= "[MD] [mini] Help Select v4.0.ani"
work		= "[MD] [mini] Working In Background v4.0.ani"
busy		= "[MD] [mini] Busy v4.0.ani"
cross		= "[MD] [mini] Precision Select v4.0.ani"
text		= "[MD] [mini] Text Select v4.0.ani"
hand		= "[MD] [mini] Handwriting v4.0.ani"
unavailiable	= "[MD] [mini] Unavailable v4.0.ani"
vert		= "[MD] [mini] Vertical Resize v4.0.ani"
horz		= "[MD] [mini] Horizontal Resize v4.0.ani"
dgn1		= "[MD] [mini] Diagonal Resize 1 v4.0.ani"
dgn2		= "[MD] [mini] Diagonal Resize 2 v4.0.ani"
move		= "[MD] [mini] Move v4.0.ani"
alternate	= "[MD] [mini] Alternate Select v4.0.ani"
link		= "[MD] [mini] Link Select v4.0-static.cur"  
```

***  

未完待续