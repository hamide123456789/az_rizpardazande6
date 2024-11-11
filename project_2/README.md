## موضوع آزمایش : نمایش حروف انگلیسی با سون سگمنت 

### گزارش کار 

ماژول سون سگمنت از هفت LED تشکیل شده است که با روشن و خاموش کردن هر کدام می‌توان اعداد، حروف و شکلک‌های مختلف را نمایش داد. هر LED دارای پایه خاصی است که امکان کنترل جداگانه را فراهم می‌کند. تصویر الگوی سون سگمنت و پایه‌های مربوطه در پایین نشان داده شده است

---

### کد برنامه

```cpp
int sequence[][7] = {
  {1,1,1,0,1,1,1},  
  {1,0,0,1,1,1,0},  
  {1,0,0,1,1,1,1},  
  {1,0,0,0,1,1,1},  
  {0,1,1,0,1,1,1},  
  {0,0,0,1,1,1,0},  
  {1,1,0,0,1,1,1},  
};

void printLetter (int number) {
  for (int i = 0; i < 7; i++) {
    digitalWrite(1+i,sequence[number][i]);
    }
  }

void setup() {
  for (int i = 1; i < 8; i++) {
    pinMode(i, OUTPUT);
    }
}

void loop() {
  for (int i = 0; i < 7; i++) {
    printLetter(i);
    delay(1000);
    }
}
```

### تصویر مدار


![pic micro](/pic/microprocessor2.jpg)
![pic micro](/pic/microprocessor2_2.jpg)




---

### شماتیک مدار 

![pic schematic](/pic/schematic_1.jpg)


