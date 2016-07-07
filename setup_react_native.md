# การติดตั้ง React Native


![](images/React-native.png)

React Native คืออะไร ? 
React Native มันคือ Framework ชนิดหนึ่งที่มีความสามารถในการสร้าง App Android และ iOS แล้วเจ้าตัว React-Native มันดีอย่างไรหล่ะ? เดี๋ยวเราไปดูกัน


{% video %} https://www.youtube.com/watch?v=juWhxCz1Wmg {% endvideo %}


 ###ขั้นตอนการติดตั้ง React Native


 1. ติดตั้ง HomeBrew สำหรับเครื่อง Mac โดยใช้คำสั่งดังต่อไปนี้ใน command line
 
      ```/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"```
  
 2. ใช้ HomeBrew ในการ Install Node.js 
 
  ```brew install node```
  
 3. ใช้ npm ในการ Install React Native

    ```npm install -g react-native-cli```
  
 
###  มาลองสร้าง App จาก React-Native กันดู

  หลังจากติดตั้งเสร็จเรียบร้อยเรามาลองสร้างโปรเจค React-Native ง่าย ๆ กันครับ

เริ่มสร้างสร้าง Floder ที่เราจะใช้ในการเก็บแอปของเรากันก่อนนะครับ

![](images/Screen Shot 2559-06-21 at 14.59.33.png)

หลังจากนั้นเปิดโปรแกรม Terminal พิมพ์ cd เพื่อจะเข้า Directory และทำการดึงโฟลเดอร์ที่สร้าง ReactApp เข้าไปใน Terminal แล้วกด Enter 1 ทีครับ

 ![](images/react02.png)
 
 ![](images/React03.png)
 
หลังจากที่เราเข้ามาใน Directory แล้วก็ทำการสร้างโปรเจคของเราขึ้นมาครับโดยใช้คำสั่ง

```react-native init CmmcReact```


