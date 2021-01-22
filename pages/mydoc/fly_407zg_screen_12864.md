---
title: Connecting a 12864 screen to a Fly-407ZG
tags: []
keywords: 
last_updated: 15/01/2021
summary: "Connecting a 12864 screen to a Fly-407ZG"
sidebar: mydoc_sidebar
permalink: fly_407zg_screen_12864.html
folder: mydoc
comments: false
toc: false
datatable: true
---

## Overview

## Overview

The information here is aimed at connecting a RepRap 12864 display but it can also be applied to other 12864 displays (as long as they are ST7567 or ST7920 based).

## Board.txt modifications

Add the following lines to the board.txt file

```
lcd.encoderPinA=C.4
lcd.encoderPinB=C.5
lcd.encoderPinSw=E.15
lcd.lcdCSPin=E.12
lcd.spiChannel=3
softwareSPI.pins={E.10, NoPin, E.14}
```

## Config.g changes

Add the following line to the end of your config.g

```
M918 P1 E4 F100000
```

## Menu Files

Menu files must be uploaded to allow the display to generate the correct information. This can be done in two ways.
First, obtain the recommended menu files from [here](https://github.com/jadonmmiller/UltimateDuetMenuSystem/releases/)

### Method 1 - Wifi Mode only

Extract the contents of the zip file you downloaded above and place them in a folder called "Menu" on the SD card of the Fly-407ZG. 

### Method 2

Activate the display using the config.g changes above.  
A side menu called "Display" should appear in DWC. Navigate to it and upload the zip file.  