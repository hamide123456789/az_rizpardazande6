## موضوع آزمایش: نمایش اعداد با سون سگمنت 

### گزارش کار :

ماژول سون سگمنت شامل هفت LED مجزا است که با روشن و خاموش کردن هر کدام می‌توان اعداد یک رقمی، حروف انگلیسی و برخی شکل‌ها را نمایش داد. هر LED دارای یک پایه مخصوص است که امکان کنترل جداگانه هر LED را فراهم می‌کند. در تصویر زیر می‌توانید الگوی سون سگمنت و پایه‌های مرتبط با هر LED را مشاهده کنید.

---

### الگوی چینش LED ها در سون سگمنت 📍

<br>

<div align="center">
<img src="/media/7segment-pinout.png" width="200px" height="400px">
</div>

---

### کد برنامه

```cpp
int sequence[][7] = {
  {1,1,1,1,1,1,0},  
  {0,1,1,0,0,0,0},  
  {1,1,0,1,1,0,1},  
  {1,1,1,1,0,0,1},  
  {0,1,1,0,0,1,1},  
  {1,0,1,1,0,1,1},  
  {1,0,1,1,1,1,1},  
  {1,1,1,0,0,0,0},  
  {1,1,1,1,1,1,1},  
  {1,1,1,1,0,1,1},  
};

void printNumber (int number) {
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
  for (int i = 0; i < 10; i++) {
    printNumber(i);
    delay(1000);
    }
}
```

### تصویر مدار

<br>

<div align="center">
<img src="/pic/microprocessor_1.jpg">
</div>

---

### شماتیک مدار 

<br>

<div align="center">
<img src="/pic/schematic_1.jpg" width="600px" height="300px">
</div>
