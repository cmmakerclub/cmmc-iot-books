![](https://i1.wp.com/farm4.staticflickr.com/3956/18553130984_b97117b088_z.jpg?zoom=2&resize=474%2C521&ssl=1)# การเริ่มต้นใช้งาน ESP8266 ผ่านทาง Arduino IDE (ตอนที่ 1 – ติดตั้ง Arduino IDE กับ ESP8266 พร้อม flash โปรแกรม)

1. ติดตั้ง Arduino IDE เวอร์ชั้น 1.6.5 หรือ ใหม่กว่า โดย Arduino IDE สามารถ Support  Windows Mac OS X Linux ทั้ง 32bit และ 64 bit ซึ่งหา Download ตัวติดตั้งได้จาก [https://www.arduino.cc/en/main/software](https://www.arduino.cc/en/main/software)![](https://i0.wp.com/farm1.staticflickr.com/281/18551638833_b79027b7f3_z.jpg)
สำหรับการติดตั้ง Arduino IDE บน Windows จะมีแบบให้เลือกทั้ง แตกไฟล์ใช้ได้เลย (ZIP file for non admin install)หรือ ติดตั้งเหมือน โปรแกรมทั่วๆไป (Installer) หากติดตั้งเรียบร้อยแล้ว ให้เปิด Arduino IDE ขึ้นมาจะได้หน้าตาแบบนี้เลยครับ![](https://i1.wp.com/farm1.staticflickr.com/285/18984844170_15ffb0b09c_z.jpg?zoom=2&resize=474%2C546&ssl=1)

2. ติดตั้ง Broad ESP8266 ลงบน Arduino IDE
  * กดเลือก Menu ไปที่ **File** >> **Preferences**
![](https://i1.wp.com/farm4.staticflickr.com/3765/19166802792_494dd9b621_z.jpg?zoom=2&resize=474%2C541&ssl=1)
  * จะขึ้นหน้าต่าง Preferences  ให้สังเกตุในช่อง Additional Board Manger URLs:
  ![](https://i2.wp.com/farm1.staticflickr.com/277/19179043611_92157254b2_z.jpg?zoom=2&resize=474%2C314&ssl=1)
  
    ในส่วนของ Additional Board Manger  บทความนี้ผมจะใช้ Boards Manager ของ Community ESP8266

  * ใส่ URL >> ลงใน Addition Board Manager URLs: ดังนี้ http://arduino.esp8266.com/package_esp8266com_index.json
  ![](https://i2.wp.com/farm1.staticflickr.com/513/19179168771_4776115428_z.jpg?zoom=2&resize=474%2C313&ssl=1)
  
  จากนั้นกด OK

  * ไปที่ Menu Tools >> Boar: “Arduino…” >> Board Manager…
   ![](https://i1.wp.com/farm4.staticflickr.com/3956/18553130984_b97117b088_z.jpg?zoom=2&resize=474%2C521&ssl=1)

  จะขึ้นหน้าต่าง Boards Manager
  ![](https://i2.wp.com/farm4.staticflickr.com/3903/19175678255_1cbc37ca20_z.jpg?zoom=2&resize=474%2C264&ssl=1)
  
  * เลือก Type เป็น Contributed จะแสดง Boards ของ ESP8266 เลือก Boards และกด Install 
  ![](https://i2.wp.com/farm1.staticflickr.com/309/19170105272_58b264f65a_z.jpg?zoom=2&resize=474%2C265&ssl=1)
  แล้วรอ สัก 2-3 ครู่ ตัวโปรแกรมจะโหลด Boards ESP8266 ให้ ขนาดไฟล์ประมาณ 100 MB และติดตั้งให้เอง
  ![](https://i2.wp.com/farm1.staticflickr.com/277/18988384088_fd7d378d33_z.jpg?zoom=2&resize=474%2C267&ssl=1)
  เมื่อเราติดตั้งบอร์ด ESP8266 เสร็จเรียบร้อยแล้ว ให้ปิดโปรแกรม Arduino IDE ก่อน แล้วจึงเปิดขึ้นมาใหม่
* เมื่อเปิดโปรแกรม Arduino IDE ขึ้นมาใหม่แล้ว ให้ลองเลือกไปที่ Menu Tools >> Board: “…..” ซึ่งจะพบว่า มี Menu สำหรับเลือกใช้งาน ESP8266 กับ Arduino IDE ขึ้นมาให้เลือกใช้งานแล้วครับ
