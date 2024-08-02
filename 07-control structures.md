# 7. Control Structures

## 1. if, else, elif statements

โครงสร้างการตัดสินใจ if, else และ elif เป็นส่วนสำคัญในการเขียนโปรแกรมที่ต้องมีการตัดสินใจหรือแยกกรณี โดยมีรายละเอียดดังนี้:

1. if statement:
   - ใช้สำหรับตรวจสอบเงื่อนไข
   - ถ้าเงื่อนไขเป็นจริง (True) คำสั่งภายใน if block จะถูกทำงาน

```python
age = 18
if age >= 18:
    print("คุณเป็นผู้ใหญ่แล้ว")
```

2. else statement:
   - ใช้ร่วมกับ if
   - ทำงานเมื่อเงื่อนไขใน if เป็นเท็จ (False)

```python
temperature = 25
if temperature > 30:
    print("อากาศร้อน")
else:
    print("อากาศไม่ร้อน")
```

3. elif statement:
   - ย่อมาจาก "else if"
   - ใช้เมื่อต้องการตรวจสอบหลายเงื่อนไข
   - สามารถมีได้หลาย elif ต่อกัน

```python
score = 75
if score >= 80:
    print("เกรด A")
elif score >= 70:
    print("เกรด B")
elif score >= 60:
    print("เกรด C")
else:
    print("เกรด F")
```

ตัวอย่างเพิ่มเติม: โปรแกรมคำนวณค่า BMI และแสดงผลการประเมิน

```python
def calculate_bmi(weight, height):
    return weight / (height ** 2)

def evaluate_bmi(bmi):
    if bmi < 18.5:
        return "น้ำหนักน้อยเกินไป"
    elif 18.5 <= bmi < 25:
        return "น้ำหนักปกติ"
    elif 25 <= bmi < 30:
        return "น้ำหนักเกิน"
    else:
        return "อ้วน"

# รับข้อมูลจากผู้ใช้
weight = float(input("กรุณาป้อนน้ำหนักของคุณ (กิโลกรัม): "))
height = float(input("กรุณาป้อนส่วนสูงของคุณ (เมตร): "))

# คำนวณ BMI
bmi = calculate_bmi(weight, height)

# ประเมินผล BMI
result = evaluate_bmi(bmi)

# แสดงผลลัพธ์
print(f"ค่า BMI ของคุณคือ: {bmi:.2f}")
print(f"ผลการประเมิน: {result}")

```

โปรแกรมนี้แสดงให้เห็นการใช้ if-elif-else statements ในการประเมินค่า BMI ซึ่งมีหลายเงื่อนไข โดยแต่ละเงื่อนไขจะมีการกระทำที่แตกต่างกัน

ในโปรแกรมนี้ เราใช้:

1. ฟังก์ชัน `calculate_bmi()` สำหรับคำนวณค่า BMI
2. ฟังก์ชัน `evaluate_bmi()` ใช้ if-elif-else statements เพื่อประเมินผล BMI
3. รับข้อมูลน้ำหนักและส่วนสูงจากผู้ใช้
4. คำนวณและแสดงผลลัพธ์

## 2. for และ while loops

Loops หรือการวนซ้ำเป็นโครงสร้างพื้นฐานที่สำคัญในการเขียนโปรแกรม ช่วยให้เราสามารถทำงานซ้ำๆ ได้อย่างมีประสิทธิภาพ ใน Python มี loops สองประเภทหลักคือ for loop และ while loop

### 2.1 for loop

for loop ใช้สำหรับการวนซ้ำผ่านลำดับของสิ่งต่างๆ เช่น list, tuple, dictionary, string หรือ range

โครงสร้างพื้นฐาน:

```python
for item in sequence:
    # คำสั่งที่จะทำซ้ำ
```

ตัวอย่าง:

1. วนซ้ำผ่าน list:

```python
fruits = ["แอปเปิ้ล", "กล้วย", "ส้ม"]
for fruit in fruits:
    print(fruit)
```

2. ใช้ range() function:

```python
for i in range(5):  # จะพิมพ์ตัวเลข 0 ถึง 4
    print(i)
```

3. วนซ้ำผ่าน dictionary:

```python
person = {"name": "สมชาย", "age": 30, "city": "กรุงเทพ"}
for key, value in person.items():
    print(f"{key}: {value}")
```

### 2.2 while loop

while loop ใช้เพื่อทำซ้ำชุดคำสั่งตราบเท่าที่เงื่อนไขที่กำหนดยังเป็นจริง

โครงสร้างพื้นฐาน:

```python
while condition:
    # คำสั่งที่จะทำซ้ำ
```

ตัวอย่าง:

1. นับถอยหลัง:

```python
count = 5
while count > 0:
    print(count)
    count -= 1
print("ปล่อยจรวด!")
```

2. รับข้อมูลจากผู้ใช้จนกว่าจะถูกต้อง:

```python
password = ""
while password != "1234":
    password = input("กรุณาป้อนรหัสผ่าน: ")
print("รหัสผ่านถูกต้อง")
```

ตัวอย่างการใช้ for และ while loops ในโปรแกรมที่ซับซ้อนขึ้น:

```python
import random

def number_guessing_game():
    # สุ่มตัวเลขระหว่าง 1 ถึง 100
    secret_number = random.randint(1, 100)
    attempts = 0
    max_attempts = 10

    print("ยินดีต้อนรับสู่เกมทายตัวเลข!")
    print(f"ฉันกำลังคิดถึงตัวเลขระหว่าง 1 ถึง 100 คุณมี {max_attempts} ครั้งในการทาย")

    while attempts < max_attempts:
        try:
            guess = int(input("ทายตัวเลข: "))
            attempts += 1

            if guess < secret_number:
                print("น้อยเกินไป! ลองอีกครั้ง")
            elif guess > secret_number:
                print("มากเกินไป! ลองอีกครั้ง")
            else:
                print(f"ยินดีด้วย! คุณทายถูกภายใน {attempts} ครั้ง")
                return

            if attempts < max_attempts:
                print(f"คุณเหลือโอกาสทายอีก {max_attempts - attempts} ครั้ง")

        except ValueError:
            print("กรุณาป้อนตัวเลขที่ถูกต้อง")

    print(f"เสียใจด้วย คุณใช้โอกาสหมดแล้ว ตัวเลขที่ถูกต้องคือ {secret_number}")

# เริ่มเกม
number_guessing_game()

```

ในโปรแกรมนี้ เราใช้ while loop เพื่อให้ผู้เล่นสามารถทายตัวเลขได้หลายครั้งจนกว่าจะถูกหรือหมดโอกาสทาย โปรแกรมนี้แสดงให้เห็นการใช้ while loop ในสถานการณ์ที่เราไม่ทราบจำนวนรอบที่แน่นอนล่วงหน้า

ส่วนประกอบสำคัญของโปรแกรม:

1. ใช้ `random.randint()` เพื่อสุ่มตัวเลข
2. ใช้ while loop เพื่อให้ผู้เล่นทายได้หลายครั้ง
3. ใช้ if-elif-else เพื่อตรวจสอบคำตอบและให้คำแนะนำ
4. ใช้ try-except เพื่อจัดการกับข้อผิดพลาดในกรณีที่ผู้ใช้ป้อนข้อมูลไม่ถูกต้อง

## 3. การใช้ break และ continue

break และ continue เป็นคำสั่งที่ใช้ควบคุมการทำงานของ loops ใน Python

break:

- ใช้เพื่อออกจาก loop ทันที
- มักใช้เมื่อพบเงื่อนไขที่ต้องการหยุดการทำงานของ loop

ตัวอย่างการใช้ break:

```python
for i in range(1, 11):
    if i == 5:
        break
    print(i)
# ผลลัพธ์: 1 2 3 4
```

continue:

- ใช้เพื่อข้ามการทำงานในรอบปัจจุบันและไปทำงานในรอบถัดไป
- มักใช้เมื่อต้องการข้ามบางเงื่อนไขในการทำงานของ loop

ตัวอย่างการใช้ continue:

```python
for i in range(1, 6):
    if i == 3:
        continue
    print(i)
# ผลลัพธ์: 1 2 4 5
```

การใช้ break และ continue ใน while loop:

```python
count = 0
while True:
    count += 1
    if count == 3:
        continue
    if count == 5:
        break
    print(count)
# ผลลัพธ์: 1 2 4
```

ตัวอย่างการใช้ break และ continue ในโปรแกรมที่ซับซ้อนขึ้น:

```python
def is_prime(n):
    if n < 2:
        return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True

def find_primes(start, end):
    primes = []
    for num in range(start, end + 1):
        if num > 1000:  # ใช้ break เพื่อจำกัดการค้นหา
            break
        if num < 2:
            continue  # ใช้ continue เพื่อข้ามจำนวนที่น้อยกว่า 2
        if is_prime(num):
            primes.append(num)
    return primes

# ทดสอบโปรแกรม
start = int(input("ป้อนจำนวนเริ่มต้น: "))
end = int(input("ป้อนจำนวนสุดท้าย: "))

prime_numbers = find_primes(start, end)
print(f"จำนวนเฉพาะระหว่าง {start} และ {end} คือ:")
print(prime_numbers)
print(f"พบจำนวนเฉพาะทั้งหมด {len(prime_numbers)} จำนวน")

```

ในโปรแกรมนี้:

- ใช้ continue เพื่อข้ามจำนวนที่น้อยกว่า 2
- ใช้ break เพื่อหยุดการค้นหาเมื่อเจอจำนวนที่มากกว่า 1000
- ฟังก์ชัน is_prime() ใช้การหารเพื่อตรวจสอบว่าเป็นจำนวนเฉพาะหรือไม่
- ฟังก์ชัน find_primes() ใช้ loop เพื่อค้นหาจำนวนเฉพาะในช่วงที่กำหนด

โปรแกรมนี้แสดงให้เห็นการใช้ break และ continue ในบริบทของการแก้ปัญหาจริง โดยใช้ continue เพื่อเพิ่มประสิทธิภาพและ break เพื่อจำกัดขอบเขตการค้นหา
