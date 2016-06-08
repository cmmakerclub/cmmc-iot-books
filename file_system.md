# File  System

## Table of Contents
  * [Uploading files to file system](#uploading-files-to-file-system)
  * [Flash layout](#flash-layout)


## การอัพโหลดไฟล์ขึ้น ESP8266 

*ESP8266FS* is a tool which integrates into the Arduino IDE. It adds a menu item to *Tools* menu for uploading the contents of sketch data directory into ESP8266 flash file system.

- ดาวน์โหลดเครื่องมืออัพโหลดไฟล์: https://github.com/esp8266/arduino-esp8266fs-plugin/releases/download/0.2.0/ESP8266FS-0.2.0.zip.
- แตกไฟล์เข้าไปที่โฟล์เดอร์ `<home_dir>Documents/Arduino/tools/ESP8266FS/tool/esp8266fs.jar`

![esp8266-fs-tools](esp8266-fs-tools.JPG)

- Restart Arduino IDE
- เปิดหรือสร้าง Arduino Sketch ขึ้นมา และเข้าไปโปรเจ็ค (เลือกเมนู Sketch > Show Sketch Folder) 

![show-sketch-folder](show-sketch.jpg)

- สร้างโฟล์เดอร์ `data` ขึ้นมา และเอาไฟล์ที่ต้องการอัพโหลดเข้าไปใน ESPresso Lite วางไว้ใน `data`
- เลือกบอร์ดให้ถูกต้อง และปิด Serial Monitors
- เลือกเมนู Tools > ESP8266 Sketch Data Upload. เมื่ออัพโหลดเสร็จแล้วจะขึ้นว่า  `SPIFFS Image Uploaded`



## Flash layout

Even though file system is stored on the same flash chip as the program, programming new sketch will not modify file system contents. This allows to use file system to store sketch data, configuration files, or content for Web server.

The following diagram illustrates flash layout used in Arduino environment:

    |--------------|-------|---------------|--|--|--|--|--|
    ^              ^       ^               ^     ^
    Sketch    OTA update   File system   EEPROM  WiFi config (SDK)

File system size depends on the flash chip size. Depending on the board which is selected in IDE, you have the following options for flash size:

Board | Flash chip size, bytes | File system size, bytes
------|-----------------|-----------------
Generic module | 512k | 64k, 128k
Generic module | 1M | 64k, 128k, 256k, 512k
Generic module | 2M | 1M
Generic module | 4M | 3M
Adafruit HUZZAH | 4M | 1M, 3M
ESPresso Lite 1.0 | 4M | 1M, 3M
ESPresso Lite 2.0 | 4M | 1M, 3M
NodeMCU 0.9    | 4M | 1M, 3M
NodeMCU 1.0    | 4M | 1M, 3M
Olimex MOD-WIFI-ESP8266(-DEV)| 2M | 1M
SparkFun Thing | 512k | 64k
SweetPea ESP-210 | 4M | 1M, 3M
WeMos D1 & D1 mini | 4M | 1M, 3M
ESPDuino | 4M | 1M, 3M

**Note:** to use any of file system functions in the sketch, add the following include to the sketch:

```c++
#include "FS.h"
```

