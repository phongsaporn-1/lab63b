# การทดลองที่ 7 การเขียนโปรแกรมวนลูป​ เพื่อให้ไฟLEDวิ่ง
## วัตถุประสงค์
1. เพื่อศึกษาเกี่ยวกับเขียนโปรแกรมวนลูป
2. เพื่อศึกษาเกี่ยวกับไมโครคอนโทรลเลอร์
## อุปกรณ์ที่ใช้
1. NodeMCU V2 LUA based ESP8266-12E
2. บอร์ดทดลอง Wifi NodeMCU V2 CP2102 LUA based ESP8266-12F/N
3. สาย Micro USB Type B to USB 2.0 Type A 
4. LED ขนาด 5mm สีแดง จำนวน 5 ดวง
5. บอร์ดทดลอง Breadboard 830 Point
6. Resistor ตัวต้านทาน 330 Ohm 1/4W Metal film 1% 
7. สายไฟจัมเปอร์ ผู้-ผู้ ยาว 20cm. 
## ศึกษาข้อมูลเบื้องต้น
1.​ การเขียนโปรแกรม​ด้วยลูป for​ ภาษาC
## วิธีการทำการทดลอง 
1. นำไมโครคอนโทรเลอร์ต่อเข้ากับ USB
![image](https://user-images.githubusercontent.com/80881033/113172281-7ca44700-9272-11eb-86d8-f3bec5079730.png)

2. เลือกโค้ดที่ต้องการใช้
```
int led1 = D0;
int led2 = D1;
int led3 = D2;
int led4 = D3;
int led5 = D4;
void setup() {
  pinMode(led1, OUTPUT);
  pinMode(led2, OUTPUT);
  pinMode(led3, OUTPUT);
  pinMode(led4, OUTPUT);
  pinMode(led5, OUTPUT);
  Serial.begin(9600);
  digitalWrite(led1, LOW);
  digitalWrite(led2, LOW);
  digitalWrite(led3, LOW);
  digitalWrite(led4, LOW);
  digitalWrite(led5, LOW);
}

void loop() {
  Serial.println("Test"); 
  for (int x = 1; x < 5; x++) { 
    Serial.print("X = "); 
    Serial.println(x); 
    if (x == 1) {
      digitalWrite(led1, HIGH);
    }
    if (x == 2) {
      digitalWrite(led2, HIGH);
    }
    if (x == 3) {
      digitalWrite(led3, HIGH);
    }
    if (x == 4) {
      digitalWrite(led4, HIGH);
    }
    delay(100);
  }
  for (int x = 4; x < 0; x++) { 
    Serial.print("X = "); // 
    Serial.println(x); 
    if (x == 1) {
      digitalWrite(led1, LOW);
    }
    if (x == 2) {
      digitalWrite(led2, LOW);
    }
    if (x == 3) {
      digitalWrite(led3, LOW);
    }
    if (x == 4) {
      digitalWrite(led4, LOW);
    }
    delay(100);
  }

}
```
3. อัปโหลดโค้ดที่เลือกลงไมโครคอนโทรลเลอร์
4. พิมพ์คำสั่งรัน
![image](https://user-images.githubusercontent.com/80881033/113172330-89c13600-9272-11eb-8c23-46239a356d44.png)

## การบันทึกผลการทดลอง
เมื่อทำการรันคำสั่ง​ ไฟ​LEDก็จะติดและดับตามเงื่อนไขลูปที่กำหนดไว้​ 
## อภิปรายผลการทดลอง
จากการทดลองจะพบว่าไฟLEDจะวิ่งตามลูปที่ตั้งไว้​ 
## คำถามหลังการทดลอง
* คำถาม:ถ้าเราต้องการให้ลูปมีการวนนานขึ้นต้องทำอย่างไร
* คำตอบ:แก้โค้ด​ for​ ตรง​ int x=1 ; x < 4 ให้มากกว่า 4 แล้วต้องเพิ่มลูปด้วย
