# Meshtastic 低成本控制器开源项目
## 项目简介
基于Meshtastic协议的低成本通信控制器解决方案，集成太阳能充电、GPS定位和LoRa通信功能，适用于物联网、野外通信等场景。尤其使用与太阳能节点。
并且这个项目一个PCB就可以兼容几乎市场上可以买到的（可以薅羊毛的）所有模块。

该项目源自https://github.com/gargomoma/fakeTec_pcb.

## 与fake对比

|![image](image/20250114_01.JPG)  

## 功能模块
### 1. 集成太阳能充电

  - [CN3163充电管理IC](https://item.szlcsc.com/582671.html?fromZone=s_s__%2522C559031%2522&spm=sc.gb.xh1.zy.n___sc.hm.hd.ss&t=1739525886502&s=1739525886502&lcsc_vid=FgJaXlFRTwdWBgAAEVBdAlEARwMIVVxUFVENAQdTRAAxVlNVTlRcUlxfR1FbXjtW)
  
  - 温度保护范围：0-55°C（板载NTC设定）
  
  - 可拆除NTC,替换为电池内部NTC
  
  - 限流电阻：1.2KΩ（1000mA）
  
  - 充电恒压电压：4.2V
  
  - 输入电压:4.4~6V
  
  - 充电状态和充电结束状态双指示输出


### 2. 集成外部通知部件 External Notification

蜂鸣器
- 通过MOS管驱动蜂鸣器（增加了续流二极管)（38）
  需要在Device页面以及External Notification页面同时配置为38

LED
- 外部白色LED（33）
  只需在External Notification页面配置为33

用户按键
- 按键KEY，引脚（32）默认
  无需配置

GPS开关
- 通过MOS管驱动GPS开关
  Position页配置TX为"20"、RX为"22"、EN为"24"


### 3. GPS硬件
| 组件 | 型号 | 备注 |
| :------------ | :---------------------------- | :---------------------------- |
| 主控 | ProMicro NRF52840 | 购买链接 |
| GPS | ATGM336H-5N71 | [gps模块北斗3单片机ATGM336H-5N71模块+天线](https://item.taobao.com/item.htm?id=649721823963&_u=e1fg9to3077) |
| 屏幕 | 0.96" SSD1306 OLED | 购买链接 |



### 4. LoRa模块
LoRa模块支持
| 厂家 | 型号 | 备注 |
| :------------ | :---------------------------- | :---------------------------- |
| 成都亿佰特 | E22-400M22S | [购买链接](https://item.taobao.com/item.htm?id=571626367408&_u=e1fg9toef8a) |
| 成都亿佰特 | E22-400MM22S | [购买链接](https://item.taobao.com/item.htm?id=571626367408&_u=e1fg9toef8a) |
| 深圳硅传 | SX1268ZTR4(433MHz)_拿样(含弹簧) | [购买链接](https://item.taobao.com/item.htm?id=631724138123&_u=e1fg9to418f) |
| 河南安信可 | SX1268_Ra-01S含弹簧天线 | [购买链接](https://item.taobao.com/item.htm?id=627657133308&_u=e1fg9toe418) |
| 惠特自动化 | RA62模块SX1262(433-510MHz) | 没有测试,理论上可以用 [购买链接](https://item.taobao.com/item.htm?id=687692791680&_u=e1fg9toe418) |

如果买 安信可SX1268_Ra-01S含弹簧天线,买到的天线是433的话,自己剪去3圈半就变成480了.


### 5. 版本更新
v1.1 改进内容

- 增加MOS管下拉电阻，消除漏电流

- GPS插座排序修改可以直接对ATGM336H模块

- 太阳能充电电流提升至1A,注意电池容量小于1Ah的需要把电流改小，一般是电池容量的0.2~0.5倍较为合适

- 增加了MeshCN LOGO 

### 6. 快速入门

硬件焊接指南

|![image](image/20250114_003653.JPG)  
|![image](image/20250114_003659.JPG)  
|![image](image/20250114_005227.JPG)  
|![image](image/20250114_005517.JPG)  

固件烧录步骤

基础配置说明

PCB实物图

|![image](image/20250115_203856.JPG)  

PCB渲染图
 
|![image](fake_yuri_PCB/PCB_TOP.JPG)  
|![image](fake_yuri_PCB/PCB_BOM.JPG)  

原理图 

功耗测试数据

通信距离实测数据

Bootloader

Meshtastic固件编译指南



已验证的硬件组合

已知兼容性问题说明



预留IO口功能定义

传感器扩展方案

社区支持信息

应用场景说明

贡献者指南

