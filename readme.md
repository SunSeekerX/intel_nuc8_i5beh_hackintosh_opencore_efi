# OpenCore for intel nuc8i5ben

![nuc8i5bek-nuc8i5beh-pb-16x9.png.rendition.intel.web.1920.1080](./assets/nuc8i5bek-nuc8i5beh-pb-16x9.png.rendition.intel.web.1920.1080.webp)

## 简介

完美 😀。

|       Key        |         Value          |
| :--------------: | :--------------------: |
| OpenCore version |         0.8.9          |
|  MacOS version   | Ventura 13.2.1 (22D68) |

## Bios 设置

Devices -> USB -> Port Device Charging Mode: off
Devices -> USB -> USB Legacy -> Disabled
Security -> Thunderbolt Security Level: Legacy Mode
Power -> Wake on LAN from S4/S5: Stay Off
Boot -> Boot Configuration -> Network Boot: Disable
Boot -> Secure Boot -> Disable

## 安装说明

- **我的是占用了读卡器的硬改版本里面有博通网卡驱动，如果你是英特尔网卡需要更换为英特尔网卡驱动**
- 记得换三码，里面没有自带的
- 不要换机型，否则 usb 接口无法使用，需要替换 USBPorts.kext 内 plist 的机型值，你会写代码的话很简单打开改下两个地方就行
- 已经用来写了好几年的代码，没啥问题。能开发，这个项目也是在 mac 下系统下传上来的
- github 星星最多的 efi 我也用过，用起来比现在配置的卡。不知道啥问题，如果我的 efi 有问题你们也可以看看：[https://github.com/zearp/Nucintosh](https://github.com/zearp/Nucintosh)

## 硬件

|   Key    |                                     Value                                     | Other      |
| :------: | :---------------------------------------------------------------------------: | ---------- |
|   CPU    |          Intel® Core™ i5-8259U Processor (6M Cache, up to 3.80 GHz)           | 4c8h       |
|   显卡   |               Intel CoffeeLake-U GT3e [Iris Plus Graphics 655]                |            |
|   内存   |               Lexar LD4AS016G-H2666G - 16 GB (1 rank, 16 banks)               | x2 共 32GB |
| 无线网卡 |          Broadcom BCM43xx 1.0 (7.77.111.1 AirPortDriverBrcmNIC-1766)          | 94360cs2   |
| 有线网卡 |                    Intel(R) Ethernet Connection (6) I219-V                    |            |
|   声卡   | Realtek ALC233 @ Intel Cannon Point-LP PCH - cAVS (Audio, Voice, Speech) [D0] |            |
|   硬盘   |                             WD Blue SN570 1TB SSD                             |            |
|   接口   |          USB-C (DP1.2) X1<br/>HDMI 2.0a X1<br/>RJ45 网口 X1<br/>...           |            |

## 正常工作

- CPU 正常睿频
- 博通网卡 - 隔空投送
- 声卡
- 睡眠
- 核显正常驱动，支持缩放/夜览

## 存在的问题

- ~~开机偶发卡住，不管是进入 win 还是 mac 都有这个问题。看起来像个例，有没出现这个问题的。~~

  在 issue 有截图感觉是 usb 相关的问题，按照上面的 bios 设置没有出问题了。

## 部分系统截图

<img src="./assets/iShot_2023-02-15_14.52.14.webp" style="zoom:25%;" />

程序坞

<img src="./assets/iShot_2023-02-15_14.48.39.webp" style="zoom:25%;" />

| Describe | screenshot                                                               |
| -------- | ------------------------------------------------------------------------ |
| Nvme     | <img src="./assets/iShot_2023-02-15_14.55.15.webp" style="zoom: 50%;" /> |
| USB      | <img src="./assets/iShot_2023-02-15_14.55.00.webp" style="zoom:50%;" />  |
| 以太网   | <img src="./assets/iShot_2023-02-15_14.54.41.webp" style="zoom:50%;" />  |
| 内存     | <img src="./assets/iShot_2023-02-15_14.54.35.webp" style="zoom:50%;" />  |
| 显卡     | <img src="./assets/iShot_2023-02-15_14.54.28.webp" style="zoom:50%;" />  |
| 电源     | <img src="./assets/iShot_2023-02-15_14.54.14.webp" style="zoom:50%;" />  |
| 蓝牙     | <img src="./assets/iShot_2023-02-15_14.54.10.webp" style="zoom:50%;" />  |
| 音频     | <img src="./assets/iShot_2023-02-15_14.54.02.webp" style="zoom:50%;" />  |
| WIFI     | <img src="./assets/iShot_2023-02-15_14.53.54.webp" style="zoom:50%;" />  |

## 部分 efi 截图

| Describe | screenshot                                                                                              |
| :------: | ------------------------------------------------------------------------------------------------------- |
|   ACPI   | <img src="./assets/iShot_2023-02-15_14.43.29.webp" alt="iShot_2023-02-07_20.09.44" style="zoom:25%;" /> |
|    Dp    | <img src="./assets/iShot_2023-02-15_14.44.35.webp" alt="iShot_2023-02-07_20.09.53" style="zoom:25%;" /> |
|  Kernel  | <img src="./assets/iShot_2023-02-15_14.45.03.webp" alt="iShot_2023-02-07_20.09.44" style="zoom:25%;" /> |

## 更新日志

### 2023-02-24

- 增加了 CFGLock 查看工具，需要按住空格显示辅助工具
- 默认隐藏辅助工具，按住空格显示

## 参考

- [[OpenCore] NUC8 最新 OC EFI 持续更新（已更新至 0.8.7+13.1）](https://bbs.pcbeta.com/viewthread-1935097-1-1.html) by yippeeghost
