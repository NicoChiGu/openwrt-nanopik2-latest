# NanopiK2 S905 Openwrt固件
<img alt="Releases Downloads" src="https://img.shields.io/github/downloads/NicoChiGu/openwrt-nanopik2-latest/total?style=for-the-badge"> <img alt="Releases Date" src="https://img.shields.io/github/release-date/NicoChiGu/openwrt-nanopik2-latest?style=for-the-badge">

| 内核版本 | 固件下载 | 编译状态 |
| :-------------: | :-------------: | :-------------: |
| stable | [![](https://img.shields.io/badge/-%E4%B8%8B%E8%BD%BD-red?style=for-the-badge)](https://github.com/NicoChiGu/openwrt-nanopik2-latest/releases) | [![](https://img.shields.io/github/downloads/NicoChiGu/openwrt-nanopik2-latest/NanopiK2_stable/total?label=stable&style=for-the-badge)](#) |
| flippy+ | [![](https://img.shields.io/badge/-%E4%B8%8B%E8%BD%BD-red?style=for-the-badge)](https://github.com/NicoChiGu/openwrt-nanopik2-latest/releases) | [![](https://img.shields.io/github/downloads/NicoChiGu/openwrt-nanopik2-latest/NanopiK2_flippy/total?label=flippy+&style=for-the-badge)](#) |
| flippy+O | [![](https://img.shields.io/badge/-%E4%B8%8B%E8%BD%BD-red?style=for-the-badge)](https://github.com/NicoChiGu/openwrt-nanopik2-latest/releases) | [![](https://img.shields.io/github/downloads/NicoChiGu/openwrt-nanopik2-latest/NanopiK2_oflippy/total?label=flippy+o&style=for-the-badge)](#) |



##### use ophub/amlogic-s9xxx-openwrt repository [OPHUB/openwrt REPO](https://github.com/ophub/amlogic-s9xxx-openwrt)
##### Kernel use ophub/kernel repository [OPHUB/kernel REPO](https://github.com/ophub/kernel)
##### use haiibo/OpenWrt repository [haiibo REPO](https://github.com/haiibo/OpenWrt/)
##### 使用 ophub/amlogic-s9xxx-openwrt 库
##### 使用 haiibo/OpenWrt 库编译的Plus版进行打包
##### [恩山无线早期测试](https://www.right.com.cn/forum/thread-8261176-1-1.html)
###### amlogic S905的NanopiK2未在ophub/amlogic-s9xxx-openwrt项目中|armbian已不再为NanopiK2维护
###### 已经从代码中做了部分修改以达到NanopiK2可以正确被引导

--------------------------
### NanopiK2 固件每周五拉取打包 【此库为Action自动编译上传】
#### 固件分为 stable 和 flippy 和 Oflippy(+O) 三个内核 自行测试.
##### 旧固件链接[【天翼云盘】](#)|[【Alist】](https://alist.terata.icu/Onedrive/openwrt/build)
##### 目前测试较为稳定固件(内核6.0.7)[【Github下载】](https://github.com/NicoChiGu/nanopik2-openwrt/releases/download/openwrt_s905_k6.0.7_2022.11.04/openwrt_nanopik2_k6.0.7.img.gz)  | [【Onedrives直链】](https://alist.terata.icu/d/Onedrive/openwrt/stable/openwrt_nanopik2_k6.0.7.img.gz)

#### 开发板参数

    SoC: Amlogic S905, Quad-core ARM Cortex-A53@1.5GHz, DVFS
    GPU: Penta-core ARM Mali™-450
    RAM: 2GB DDR3
    Network Connectivity: 10/100/1000M (RTL8211F)
    Wireless：802.11 b/g/n
    Bluetooth：4.0 dual mode
    Antenna: One onboard porcelain antenna shared by both WiFi and Bluetooth. One individual IPX interface.
    IR: Onboard IR receiver
    Audio: Via HDMI/Bluetooth
    eMMC interface: eMMC socket
    I2S: 7-Pin, 2.54mm pitch pin-header
    SD: 1 x MicroSD slot
    USB Host: 4 x USB 2.0 Host, standard type A
    Micro USB: 1 x USB 2.0, OTG, power input and data transmission
    HDMI: HDMI 2.0, Type-A. It supports 4K video
    GPIO: 40-Pin, 2.54mm pitch pin-header including I2C, ADC, GPIO, UART, PWM, SPDIF and CVBS
    Serial debug port: 4-Pin, 2.54mm pitch single-row pin-header
    User Key: 1 x power key
    LED: 1 x power LED and 1 x status LED
    Power Interface: DC jack, MicroUSB
    Power Supply: DC 5V/2A
    PCB dimension: 56 x 85mm，6-layer, ENIG

<img src="https://cdn.jsdelivr.net/gh/NicoChiGu/openwrt-nanopik2-latest@main/assets/picture.png">

<br>

##### 更新可使用`晶晨宝盒`(优先备份)

- **不保证完全无 BUG！**

- **不对任何因使用本固件所遭受的任何损失承担责任！**

## 一些问题
### 1. [**Openwrt Docker 使用Bridge桥接模式无法正常访问**](https://www.gaoyaxuan.net/blog/584.html) 
#### 或将 Docker => 设置 => DockerMan设置 => 允许访问端口 **【设置为eth0】** //因单臂路由器不进行桥接网口时没有brlan这个东西

#### 单臂路由防火墙=>'iptables -t nat -I POSTROUTING -j FULLCONENAT' 或进行VLAN设置
