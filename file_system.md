# File  System

## Table of Contents
  * [Flash layout](#flash-layout)
  * [Uploading files to file system](#uploading-files-to-file-system)
  * [Filesystem information structure](#filesystem-information-structure)
  * [Directory object (Dir)](#directory-object-dir)

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

## Uploading files to file system

*ESP8266FS* is a tool which integrates into the Arduino IDE. It adds a menu item to *Tools* menu for uploading the contents of sketch data directory into ESP8266 flash file system.

- Download the tool: https://github.com/esp8266/arduino-esp8266fs-plugin/releases/download/0.2.0/ESP8266FS-0.2.0.zip.
- In your Arduino sketchbook directory, create `tools` directory if it doesn't exist yet
- Unpack the tool into `tools` directory (the path will look like `<home_dir>/Arduino/tools/ESP8266FS/tool/esp8266fs.jar`)
- Restart Arduino IDE
- Open a sketch (or create a new one and save it)
- Go to sketch directory (choose Sketch > Show Sketch Folder)
- Create a directory named `data` and any files you want in the file system there
- Make sure you have selected a board, port, and closed Serial Monitor
- Select Tools > ESP8266 Sketch Data Upload. This should start uploading the files into ESP8266 flash file system. When done, IDE status bar will display `SPIFFS Image Uploaded` message.


