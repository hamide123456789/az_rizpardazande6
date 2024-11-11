## موضوع آزمایش : اندازه گیری دما و رطوبت با سنسور DHT11 

### گزارش کار

سنسور DHT11 برای اندازه‌گیری رطوبت از حسگر خازنی استفاده می‌کند. این حسگر دارای یک صفحه فلزی و یک صفحه عایق است که با افزایش رطوبت، ظرفیت آن تغییر می‌کند و داده‌های رطوبت تولید می‌شود. همچنین، برای اندازه‌گیری دما از حسگر مقاومتی NTC استفاده می‌کند که با افزایش دما، مقاومت آن کاهش می‌یابد و داده‌های دما ارائه می‌شود
---

### کد برنامه

```cpp
#include <DHT.h>

#define DHTPIN 8
#define DHTTYPE DHT11
DHT dht(DHTPIN, DHTTYPE);
int cooler = 7;
int heater = 6;

void setup() {
  Serial.begin(9600);
  Serial.println('DHT11 test');
  dht.begin();
  pinMode(cooler, OUTPUT);
  pinMode(heater, OUTPUT);
}

void loop() {
  float humid = dht.readHumidity();
  float temp = dht.readTemperature();
  Serial.print("The Temporary is : ");
  Serial.print(temp);
  Serial.println("*C");
  Serial.print("The Humidity is : ");
  Serial.print(humid);
  Serial.println("*%");
  delay(1000);
  if (temp > 27) {
    digitalWrite(cooler, HIGH);
    digitalWrite(heater, LOW);
    }
    else if (temp < 27) {
      digitalWrite(cooler, LOW);
      digitalWrite(heater, HIGH);
      }
}
```
---

### تصویر مدار 

![pic microprocessor](/pic/microprocessor5.jpg)


---

### شماتیک مدار 


![pic schematic](/pic/schematic_5.jpg)

