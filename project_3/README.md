## موضوع آزمایش: کنترل روشنایی با استفاده از فتوسل 

### گزارش کار

فتوسل یک مقاومت نوری است که با افزایش شدت نور، مقاومت آن کاهش می‌یابد و بالعکس. برای اندازه‌گیری نور محیط با آردوینو، یک ولتاژ بالا به ورودی آنالوگ ارسال می‌کنیم و فتوسل را در مسیر قرار می‌دهیم. با کاهش نور محیط، مقاومت فتوسل افزایش می‌یابد و ولتاژ کمتری به ورودی آنالوگ ارسال می‌شود

---

### کد برنامه

```cpp
int sensor;
int led = 10;

void setup() {
  Serial.begin(9600);
  pinMode(led, OUTPUT);
}

void loop() {
  sensor = analogRead(A3);
  Serial.print("Photocell Value = ");
  Serial.println(sensor);
  delay(100);

  if (sensor > 100) {
    digitalWrite(led, LOW);
    }

   else {
    digitalWrite(led, HIGH);
    }
}
```

### تصویر مدار


![pic micro](/pic/microprocessor3.jpg)


---

### شماتیک مدار 


![pic schematic](/pic/schematic_2.jpg)

