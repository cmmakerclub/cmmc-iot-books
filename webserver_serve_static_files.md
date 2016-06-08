# Serve Static Files


```
  #include <Arduino.h>
  #include <ESP8266WiFi.h>
  #include <ESP8266WebServer.h>
  #include "FS.h"

  #define WIFI_SSID "ESPERT-002"
  #define WIFI_PASS "espertap"

  ESP8266WebServer server(80);

  void init_hardware();
  void init_fs();
  void init_webserver();
  void init_wifi();

  void setup() {
    init_hardware();
    init_wifi();
    init_fs();
    init_webserver();
  }

  void loop() {
    server.handleClient();
  }

  void init_hardware()
  {
    Serial.begin(115200);
    delay(10);
    Serial.println();
    Serial.println("Serial port initialized.");
    pinMode(LED_BUILTIN, OUTPUT);
  }

  void init_fs() {
    Serial.println("Mounting FS...");
    if (!SPIFFS.begin()) {
      Serial.println("Failed to mount file system");
      return;
    }
    Serial.println("FS mounted.");

    Serial.println("CMMC READING ROOT DIRECTORY..");
    Dir root = SPIFFS.openDir("/");

    while (root.next()) {
      String fileName = root.fileName();
      File f = root.openFile("r");
      Serial.printf("%s: %d\r\n", fileName.c_str(), f.size());
    }
  }

  void init_webserver() {
    server.serveStatic("/", SPIFFS, "/");
    server.begin();
  }

  void init_wifi() {
    char textID[30] = {'\0'};
    sprintf(textID, "ESPresso-%lu", ESP.getChipId());

    WiFi.disconnect();
    WiFi.mode(WIFI_AP_STA);
    WiFi.softAP(textID);
    delay(200);

    IPAddress myIP = WiFi.softAPIP();
    Serial.printf("AP(%s) IP address: ", textID);
    Serial.println(myIP);
    //WiFi.begin(WIFI_SSID, WIFI_PASS);
  }

```