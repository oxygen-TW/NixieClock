# Nixie Clock oxygen

> 開發緣起，在 COSCUP 2019 聽了 @yodalee 大大的演講後再加上同學的鼓勵，又覺得它超帥的啊啊啊啊啊，決定自己也來做一套，專案從大大那邊 Fork 過來。

---
<br/>

## TODO

- 將電路中 IN14 換成 IN12-A
- 打算直接使用 K155ID1
- 確認兩種不同nixie tube data sheet 腳位差異
- 硬體
    - 高壓電模組
    - 降壓模組
    - 中央控制模組
    - RTC 模組
    - Nixie tube 控制模組

- 韌體
    - RTC校正
    - 數字顯示
    - Arduino 與 ATmega328 腳位定義

---

## The Nixie Clock

![Nixie Clock](fig/v1result.jpg)

Some demo video:  
[Test Tube](https://www.youtube.com/watch?v=yUsdp3tUh6w)  
[Change WorldLine](https://www.youtube.com/watch?v=egiKm6L4Y-A)  

## Repository Structure
├── fig  
├── hardware  
│   ├── BOMmanual\_v1.0.1.csv : BOM file manually written  
│   ├── BOM\_v1.0.1.tsv : BOM file export from EasyEDA  
│   ├── layout  
│   │   ├── gerber\_v1.01 : v1.01 Gerber file  
│   │   └── gerber\_v1.02 : v1.02 Gerber file  
│   └── schematic : Schematic for [Altium](https://www.altium.com) and [EasyEDA](https://easyeda.com)  
└── software  
&emsp;&emsp;├── DS1309 : Set time into DS1309  
&emsp;&emsp;├── HC238test : Test 74HC238 works fine.  
&emsp;&emsp;├── HC4514test : Test 74HC4514 works fine.  
&emsp;&emsp;├── nixie : Source code that right now runs on my Nixie Clock  
&emsp;&emsp;├── pin1.01.h : Macro setting for v1.01 board
&emsp;&emsp;└── pin1.02.h : Macro setting for v1.02 board

## Usage
1. Order the hardware board using the Gerber file.
2. Buy materials according to BOM file.
3. The software, please copy pin\<version\>.h to pin.h inside each directory.

## CAUTION

* The BOM table may have some difference that I did not notice, please check before you order.
* v1.02 only draw on easyEDA, it does not get fabricated and tested. It might have design problem and cannot work normally. Use it carefully.
