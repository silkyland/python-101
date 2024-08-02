# Input and Output

1. การรับข้อมูล (Input):

ฟังก์ชัน input() ใช้สำหรับรับข้อมูลจากผู้ใช้ผ่านทางคีย์บอร์ด:

```python
name = input("กรุณาป้อนชื่อของคุณ: ")
print("สวัสดี, " + name)

# รับข้อมูลตัวเลข (input() จะรับเป็น string เสมอ จึงต้องแปลงเป็นตัวเลข)
age = int(input("กรุณาป้อนอายุของคุณ: "))
print("คุณอายุ", age, "ปี")

# รับข้อมูลทศนิยม
height = float(input("กรุณาป้อนส่วนสูงของคุณ (เมตร): "))
print(f"คุณสูง {height:.2f} เมตร")
```

2. การแสดงผล (Output):

   a. ใช้ฟังก์ชัน print():

   ```python
   print("Hello, World!")
   
   name = "Alice"
   age = 30
   print("ชื่อ:", name, "อายุ:", age)
   
   # การใช้ sep และ end
   print("Hello", "World", sep="-", end="!\n")
   ```

   b. การจัดรูปแบบสตริง (String Formatting):

   - f-strings (Python 3.6+):

     ```python
     name = "Bob"
     age = 25
     print(f"ชื่อ: {name}, อายุ: {age}")
     ```

   - .format() method:

     ```python
     print("ชื่อ: {}, อายุ: {}".format(name, age))
     ```

   - % operator (แบบเก่า):

     ```python
     print("ชื่อ: %s, อายุ: %d" % (name, age))
     ```

3. การจัดรูปแบบตัวเลข:

```python
pi = 3.14159
print(f"ค่า pi แบบทศนิยม 2 ตำแหน่ง: {pi:.2f}")

large_num = 1000000
print(f"ตัวเลขใหญ่: {large_num:,}")

percentage = 0.75
print(f"เปอร์เซ็นต์: {percentage:.2%}")
```

4. การแสดงผลในหลายบรรทัด:

```python
multi_line = """
นี่คือข้อความ
หลายบรรทัด
ใน Python
"""
print(multi_line)
```

5. การอ่านและเขียนไฟล์:

   a. การอ่านไฟล์:

   ```python
   # อ่านทั้งไฟล์
   with open('example.txt', 'r', encoding='utf-8') as file:
       content = file.read()
       print(content)

   # อ่านทีละบรรทัด
   with open('example.txt', 'r', encoding='utf-8') as file:
       for line in file:
           print(line.strip())
   ```

   b. การเขียนไฟล์:

   ```python
   # เขียนไฟล์ใหม่
   with open('output.txt', 'w', encoding='utf-8') as file:
       file.write("นี่คือข้อความในไฟล์\n")
       file.write("บรรทัดที่สอง\n")

   # เพิ่มข้อมูลต่อท้ายไฟล์
   with open('output.txt', 'a', encoding='utf-8') as file:
       file.write("เพิ่มข้อมูลใหม่\n")
   ```

6. การจัดการข้อผิดพลาดในการรับข้อมูล:

```python
while True:
    try:
        age = int(input("กรุณาป้อนอายุของคุณ: "))
        break
    except ValueError:
        print("กรุณาป้อนตัวเลขเท่านั้น")

print(f"คุณอายุ {age} ปี")
```

7. การใช้ argparse สำหรับรับ command-line arguments:

```python
import argparse

parser = argparse.ArgumentParser(description="โปรแกรมทดสอบ argparse")
parser.add_argument("--name", type=str, help="ชื่อของคุณ")
parser.add_argument("--age", type=int, help="อายุของคุณ")

args = parser.parse_args()

if args.name and args.age:
    print(f"สวัสดี {args.name}, คุณอายุ {args.age} ปี")
```

8. ตัวอย่างโปรแกรมที่ใช้ input และ output:

```python
def calculate_bmi():
    print("โปรแกรมคำนวณค่า BMI")
    
    weight = float(input("กรุณาป้อนน้ำหนักของคุณ (กิโลกรัม): "))
    height = float(input("กรุณาป้อนส่วนสูงของคุณ (เมตร): "))
    
    bmi = weight / (height ** 2)
    
    print(f"\nค่า BMI ของคุณคือ: {bmi:.2f}")
    
    if bmi < 18.5:
        print("คุณอยู่ในเกณฑ์น้ำหนักน้อย")
    elif 18.5 <= bmi < 25:
        print("คุณอยู่ในเกณฑ์น้ำหนักปกติ")
    elif 25 <= bmi < 30:
        print("คุณอยู่ในเกณฑ์น้ำหนักเกิน")
    else:
        print("คุณอยู่ในเกณฑ์อ้วน")

calculate_bmi()
```

การรับข้อมูลและแสดงผลเป็นส่วนสำคัญในการสร้างโปรแกรมที่โต้ตอบกับผู้ใช้ Python มีวิธีการที่หลากหลายและยืดหยุ่นในการจัดการกับ input และ output ทำให้คุณสามารถสร้างโปรแกรมที่ใช้งานง่ายและมีประสิทธิภาพ
