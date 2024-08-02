# ตัวแปรและประเภทข้อมูล

ตัวแปร (Variables):
ตัวแปรใน Python คือชื่อที่ใช้อ้างอิงถึงค่าในหน่วยความจำ Python เป็นภาษาที่มีการจัดการประเภทข้อมูลแบบไดนามิก ซึ่งหมายความว่าคุณไม่จำเป็นต้องประกาศประเภทของตัวแปรก่อนใช้งาน

การกำหนดค่าให้ตัวแปร:

```python
x = 5
name = "John"
is_student = True
```

กฎในการตั้งชื่อตัวแปร:

1. ต้องเริ่มต้นด้วยตัวอักษรหรือขีดล่าง (_)
2. ประกอบด้วยตัวอักษร ตัวเลข และขีดล่าง
3. คำนึงถึงตัวพิมพ์เล็กและใหญ่ (case-sensitive)
4. ไม่สามารถใช้คำสงวน (reserved words) ของ Python เป็นชื่อตัวแปร

ประเภทข้อมูล (Data Types):
Python มีประเภทข้อมูลพื้นฐานหลายประเภท ดังนี้:

## 1. ตัวเลขจำนวนเต็ม (Integers)

ตัวเลขจำนวนเต็มใน Python เป็นตัวเลขที่ไม่มีจุดทศนิยม สามารถเป็นได้ทั้งค่าบวก, ลบ, หรือศูนย์

a. การสร้างและใช้งานตัวเลขจำนวนเต็ม:

```python
age = 25
count = -3
zero = 0

print(type(age))  # <class 'int'>
```

b. การดำเนินการทางคณิตศาสตร์:

```python
x = 10
y = 3

print(x + y)  # 13 (บวก)
print(x - y)  # 7 (ลบ)
print(x * y)  # 30 (คูณ)
print(x / y)  # 3.3333333333333335 (หาร - ผลลัพธ์เป็น float)
print(x // y)  # 3 (หารปัดเศษลง)
print(x % y)  # 1 (หารเอาเศษ)
print(x ** y)  # 1000 (ยกกำลัง)
```

c. ฟังก์ชันที่เกี่ยวข้องกับจำนวนเต็ม:

```python
print(abs(-5))  # 5 (ค่าสัมบูรณ์)
print(pow(2, 3))  # 8 (ยกกำลัง)
print(divmod(10, 3))  # (3, 1) (ผลหารและเศษ)
```

d. การแปลงค่าเป็นจำนวนเต็ม:

```python
float_num = 3.14
string_num = "42"

print(int(float_num))  # 3
print(int(string_num))  # 42
print(int("101", 2))  # 5 (แปลงเลขฐาน 2 เป็นฐาน 10)
```

e. ขนาดของจำนวนเต็มใน Python:

Python 3 รองรับจำนวนเต็มที่มีขนาดไม่จำกัด (ขึ้นอยู่กับหน่วยความจำที่มี)

```python
big_number = 1234567890123456789012345678901234567890
print(big_number)  # 1234567890123456789012345678901234567890
```

f. การใช้เครื่องหมายคั่นหลักพัน:

```python
population = 1_000_000_000
print(population)  # 1000000000
```

g. การแปลงระหว่างระบบเลขฐาน:

```python
# แปลงเลขฐาน 10 เป็นฐานอื่นๆ
decimal = 42
print(bin(decimal))  # 0b101010 (ฐาน 2)
print(oct(decimal))  # 0o52 (ฐาน 8)
print(hex(decimal))  # 0x2a (ฐาน 16)

# แปลงจากฐานอื่นเป็นฐาน 10
print(int('101010', 2))  # 42
print(int('52', 8))  # 42
print(int('2a', 16))  # 42
```

h. ตัวอย่างการใช้งานจริง:

1. คำนวณเงินทอน:

```python
def calculate_change(price, payment):
    change = payment - price
    denominations = [1000, 500, 100, 50, 20, 10, 5, 2, 1]
    result = {}

    for denom in denominations:
        count = change // denom
        if count > 0:
            result[denom] = count
            change %= denom

    return result

price = 1234
payment = 2000

change = calculate_change(price, payment)
print("เงินทอน:")
for denom, count in change.items():
    print(f"{denom} บาท: {count} ใบ/เหรียญ")
```

2. ตรวจสอบจำนวนเฉพาะ:

การคำนวณหาจำนวนเฉพาะทางคณิตศาสตร์ที่ง่ายที่สุดคือวิธีการของ Eratosthenes หรือที่เรียกว่า "ตะแกรงของ Eratosthenes" (Sieve of Eratosthenes) ซึ่งเป็นวิธีที่มีประสิทธิภาพสำหรับการหาจำนวนเฉพาะทั้งหมดที่น้อยกว่าหรือเท่ากับจำนวนที่กำหนด
สูตรและขั้นตอน:

สร้างรายการตัวเลขตั้งแต่ 2 ถึง n (เมื่อ n คือจำนวนสูงสุดที่ต้องการตรวจสอบ)
เริ่มจากจำนวนแรก (2) และทำเครื่องหมายทุกจำนวนที่หารด้วย 2 ลงตัว (ยกเว้นตัวมันเอง)
ไปที่จำนวนถัดไปที่ยังไม่ถูกทำเครื่องหมาย และทำซ้ำขั้นตอนที่ 2
ทำซ้ำจนกว่าจะถึงรากที่สองของ n
จำนวนที่เหลือที่ไม่ถูกทำเครื่องหมายคือจำนวนเฉพาะทั้งหมด

```python
def is_prime(n):
    if n < 2:
        return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True

# ทดสอบฟังก์ชัน
for num in range(1, 20):
    if is_prime(num):
        print(f"{num} เป็นจำนวนเฉพาะ")
    else:
        print(f"{num} ไม่เป็นจำนวนเฉพาะ")
```

3. หาตัวหารร่วมมาก (Greatest Common Divisor):

```python
def gcd(a, b):
    while b:
        a, b = b, a % b
    return a

# ทดสอบฟังก์ชัน
num1 = 48
num2 = 18
result = gcd(num1, num2)
print(f"ตัวหารร่วมมากของ {num1} และ {num2} คือ {result}")
```

## 2. ตัวเลขทศนิยม (Floating-point numbers)

ตัวเลขทศนิยมใน Python เป็นตัวเลขที่มีจุดทศนิยม ใช้สำหรับแสดงค่าที่ไม่ใช่จำนวนเต็ม

a. การสร้างและใช้งานตัวเลขทศนิยม:

```python
price = 19.99
pi = 3.14159
negative_float = -0.5

print(type(price))  # <class 'float'>
```

b. การดำเนินการทางคณิตศาสตร์:

```python
x = 10.5
y = 3.2

print(x + y)  # 13.7 (บวก)
print(x - y)  # 7.3 (ลบ)
print(x * y)  # 33.6 (คูณ)
print(x / y)  # 3.28125 (หาร)
print(x // y)  # 3.0 (หารปัดเศษลง - ผลลัพธ์ยังเป็น float)
print(x % y)  # 0.8999999999999986 (หารเอาเศษ)
print(x ** y)  # 2951.4178903541086 (ยกกำลัง)
```

c. ฟังก์ชันที่เกี่ยวข้องกับตัวเลขทศนิยม:

```python
import math

print(round(3.14159, 2))  # 3.14 (ปัดเศษ)
print(math.floor(3.7))  # 3 (ปัดเศษลง)
print(math.ceil(3.2))  # 4 (ปัดเศษขึ้น)
print(math.trunc(3.7))  # 3 (ตัดเศษทศนิยมทิ้ง)
print(abs(-4.2))  # 4.2 (ค่าสัมบูรณ์)
```

d. การแปลงค่าเป็นทศนิยม:

```python
integer_num = 42
string_num = "3.14"

print(float(integer_num))  # 42.0
print(float(string_num))  # 3.14
```

e. ความแม่นยำและข้อจำกัด:

```python
print(0.1 + 0.2)  # 0.30000000000000004 (ไม่ใช่ 0.3 พอดี เนื่องจากข้อจำกัดของการแทนค่าทศนิยมในคอมพิวเตอร์)

print(1e-15)  # 1e-15 (การแสดงผลแบบวิทยาศาสตร์)
print(1e100)  # 1e+100 (ตัวเลขที่ใหญ่มาก)
```

f. การใช้งานกับโมดูล decimal สำหรับความแม่นยำสูง:

```python
from decimal import Decimal, getcontext

getcontext().prec = 6  # กำหนดความแม่นยำ
a = Decimal('0.1')
b = Decimal('0.2')
print(a + b)  # 0.300000 (แม่นยำกว่า)
```

g. การจัดรูปแบบการแสดงผลทศนิยม:

```python
pi = 3.14159265359
print(f"ค่า pi แบบ 2 ตำแหน่งทศนิยม: {pi:.2f}")  # 3.14
print(f"ค่า pi แบบ 4 ตำแหน่งทศนิยม: {pi:.4f}")  # 3.1416
```

h. ตัวอย่างการใช้งานจริง:

1. คำนวณดอกเบี้ยทบต้น:

```python
def compound_interest(principal, rate, time, n):
    """
    คำนวณดอกเบี้ยทบต้น
    principal: เงินต้น
    rate: อัตราดอกเบี้ยต่อปี (เช่น 0.05 สำหรับ 5%)
    time: ระยะเวลาในปี
    n: จำนวนครั้งที่ทบต้นต่อปี
    """
    amount = principal * (1 + rate/n) ** (n*time)
    return amount

principal = 1000
rate = 0.05
time = 5
n = 12  # ทบต้นรายเดือน

result = compound_interest(principal, rate, time, n)
print(f"เงินต้น {principal:.2f} บาท เมื่อครบ {time} ปี จะเป็น {result:.2f} บาท")
```

2. คำนวณ BMI (ดัชนีมวลกาย):

```python
def calculate_bmi(weight, height):
    bmi = weight / (height ** 2)
    return bmi

weight = 70.5  # น้ำหนักในกิโลกรัม
height = 1.75  # ส่วนสูงในเมตร

bmi = calculate_bmi(weight, height)
print(f"BMI: {bmi:.2f}")

if bmi < 18.5:
    print("น้ำหนักน้อย")
elif 18.5 <= bmi < 25:
    print("น้ำหนักปกติ")
elif 25 <= bmi < 30:
    print("น้ำหนักเกิน")
else:
    print("อ้วน")
```

3. คำนวณระยะทางระหว่างจุดสองจุด:

```python
import math

def distance(x1, y1, x2, y2):
    return math.sqrt((x2 - x1)**2 + (y2 - y1)**2)

# ทดสอบฟังก์ชัน
x1, y1 = 0, 0
x2, y2 = 3, 4

dist = distance(x1, y1, x2, y2)
print(f"ระยะทางระหว่างจุด ({x1}, {y1}) และ ({x2}, {y2}) คือ {dist:.2f}")
```

## 3. สตริง (Strings)

สตริงใน Python คือลำดับของตัวอักษรที่อยู่ในเครื่องหมายคำพูด สามารถใช้ได้ทั้งเครื่องหมายคำพูดเดี่ยว (') หรือคู่ (") โดยมีคุณสมบัติและการใช้งานที่สำคัญดังนี้:

1. การสร้างสตริง:

```python
single_quoted = 'นี่คือสตริงที่ใช้เครื่องหมายคำพูดเดี่ยว'
double_quoted = "นี่คือสตริงที่ใช้เครื่องหมายคำพูดคู่"
multi_line = """นี่คือสตริงหลายบรรทัด
ที่ใช้เครื่องหมายคำพูดสามตัว
สามารถขึ้นบรรทัดใหม่ได้โดยไม่ต้องใช้ \n"""
```

2. การเข้าถึงตัวอักษรในสตริง:

```python
text = "Python"
print(text[0])  # แสดงผล: P
print(text[-1])  # แสดงผล: n
print(text[2:4])  # แสดงผล: th
```

3. การต่อสตริง (Concatenation):

```python
first_name = "John"
last_name = "Doe"
full_name = first_name + " " + last_name
print(full_name)  # แสดงผล: John Doe
```

4. การทำซ้ำสตริง:

```python
repeat = "Ha" * 3
print(repeat)  # แสดงผล: HaHaHa
```

5. เมธอดของสตริงที่ใช้บ่อย:

```python
text = "   Hello, World!   "
print(text.strip())  # ลบช่องว่างหน้าและหลัง: "Hello, World!"
print(text.lower())  # แปลงเป็นตัวพิมพ์เล็ก: "   hello, world!   "
print(text.upper())  # แปลงเป็นตัวพิมพ์ใหญ่: "   HELLO, WORLD!   "
print(text.replace("World", "Python"))  # แทนที่คำ: "   Hello, Python!   "
```

6. การจัดรูปแบบสตริง:

```python
name = "Alice"
age = 30

# แบบเก่า (% operator)
print("ชื่อ: %s, อายุ: %d" % (name, age))

# แบบใหม่ (format method)
print("ชื่อ: {}, อายุ: {}".format(name, age))

# f-string (ตั้งแต่ Python 3.6+)
print(f"ชื่อ: {name}, อายุ: {age}")
```

7. การหาความยาวของสตริง:

```python
text = "Python Programming"
print(len(text))  # แสดงผล: 19
```

8. การตรวจสอบสตริง:

```python
text = "Python is awesome"
print("Python" in text)  # แสดงผล: True
print(text.startswith("Py"))  # แสดงผล: True
print(text.endswith("some"))  # แสดงผล: True
```

9. การแยกสตริง:

```python
sentence = "This is a sample sentence"
words = sentence.split()
print(words)  # แสดงผล: ['This', 'is', 'a', 'sample', 'sentence']
```

10. การรวมสตริง:

```python
words = ["Python", "is", "a", "programming", "language"]
sentence = " ".join(words)
print(sentence)  # แสดงผล: Python is a programming language
```

## 4. ค่าความจริง (Boolean)

ค่าความจริง หรือ Boolean ใน Python เป็นชนิดข้อมูลที่มีเพียงสองค่าคือ True (จริง) และ False (เท็จ) ซึ่งมีความสำคัญอย่างมากในการควบคุมการทำงานของโปรแกรม โดยเฉพาะในส่วนของการตัดสินใจและการวนซ้ำ

1. การกำหนดค่า Boolean:

```python
is_student = True
has_car = False
```

2. การใช้งานในเงื่อนไข:

```python
if is_student:
    print("คุณเป็นนักเรียน")
else:
    print("คุณไม่ใช่นักเรียน")
```

3. การเปรียบเทียบ:

```python
age = 25
is_adult = age >= 18
print(is_adult)  # แสดงผล: True
```

4. ตัวดำเนินการทางตรรกศาสตร์:

```python
has_license = True
has_insurance = False

can_drive = has_license and has_insurance
print(can_drive)  # แสดงผล: False

needs_documents = has_license or has_insurance
print(needs_documents)  # แสดงผล: True

is_not_insured = not has_insurance
print(is_not_insured)  # แสดงผล: True
```

5. การแปลงค่าเป็น Boolean:

```python
print(bool(1))       # True
print(bool(0))       # False
print(bool(""))      # False
print(bool("text"))  # True
print(bool([]))      # False
print(bool([1, 2]))  # True
```

6. การใช้งานใน list comprehension:

```python
numbers = [1, 2, 3, 4, 5, 6]
even_numbers = [num for num in numbers if num % 2 == 0]
print(even_numbers)  # แสดงผล: [2, 4, 6]
```

7. เปรียบเทียบค่า Boolean:

```python
x = True
y = False

print(x == y)  # False
print(x != y)  # True
```

8. การใช้งานใน while loop:

```python
counter = 0
is_running = True

while is_running:
    print(counter)
    counter += 1
    if counter >= 5:
        is_running = False
```

9. ฟังก์ชันที่คืนค่า Boolean:

```python
def is_even(number):
    return number % 2 == 0

print(is_even(4))  # True
print(is_even(7))  # False
```

10. การใช้ Boolean ในการตรวจสอบสมาชิกของ collection:

```python
fruits = ['apple', 'banana', 'orange']
has_apple = 'apple' in fruits
print(has_apple)  # True
```

## 5. ลิสต์ (Lists)

ลิสต์เป็นโครงสร้างข้อมูลที่ใช้บ่อยมากใน Python เนื่องจากมีความยืดหยุ่นสูง สามารถเก็บข้อมูลได้หลากหลายประเภท และสามารถแก้ไขได้ (mutable)

1. การสร้างลิสต์:

```python
fruits = ["apple", "banana", "cherry"]
numbers = [1, 2, 3, 4, 5]
mixed = [1, "two", 3.0, [4, 5]]
empty_list = []
```

2. การเข้าถึงสมาชิกในลิสต์:

```python
fruits = ["apple", "banana", "cherry"]
print(fruits[0])  # apple
print(fruits[-1])  # cherry
print(fruits[1:3])  # ['banana', 'cherry']
```

3. การแก้ไขลิสต์:

```python
fruits = ["apple", "banana", "cherry"]
fruits[1] = "kiwi"
print(fruits)  # ['apple', 'kiwi', 'cherry']
```

4. การเพิ่มสมาชิกในลิสต์:

```python
fruits = ["apple", "banana"]
fruits.append("cherry")
print(fruits)  # ['apple', 'banana', 'cherry']

fruits.insert(1, "orange")
print(fruits)  # ['apple', 'orange', 'banana', 'cherry']

fruits.extend(["grape", "mango"])
print(fruits)  # ['apple', 'orange', 'banana', 'cherry', 'grape', 'mango']
```

5. การลบสมาชิกจากลิสต์:

```python
fruits = ["apple", "banana", "cherry", "date"]
removed = fruits.pop()
print(removed)  # date
print(fruits)  # ['apple', 'banana', 'cherry']

fruits.remove("banana")
print(fruits)  # ['apple', 'cherry']

del fruits[0]
print(fruits)  # ['cherry']
```

6. การหาความยาวของลิสต์:

```python
fruits = ["apple", "banana", "cherry"]
print(len(fruits))  # 3
```

7. การเรียงลำดับลิสต์:

```python
numbers = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5]
numbers.sort()
print(numbers)  # [1, 1, 2, 3, 3, 4, 5, 5, 5, 6, 9]

fruits = ["banana", "cherry", "apple"]
sorted_fruits = sorted(fruits)
print(sorted_fruits)  # ['apple', 'banana', 'cherry']
```

8. การค้นหาในลิสต์:

```python
fruits = ["apple", "banana", "cherry"]
print("banana" in fruits)  # True
print(fruits.index("cherry"))  # 2
```

9. List comprehension:

```python
squares = [x**2 for x in range(10)]
print(squares)  # [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]

even_numbers = [x for x in range(10) if x % 2 == 0]
print(even_numbers)  # [0, 2, 4, 6, 8]
```

10. การทำซ้ำผ่านลิสต์:

```python
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(f"I like {fruit}")

# ผลลัพธ์:
# I like apple
# I like banana
# I like cherry
```

11. การรวมลิสต์:

```python
list1 = [1, 2, 3]
list2 = [4, 5, 6]
combined = list1 + list2
print(combined)  # [1, 2, 3, 4, 5, 6]
```

12. การคัดลอกลิสต์:

```python
original = [1, 2, 3]
shallow_copy = original.copy()
deep_copy = [x for x in original]
```

## 6. ทูเพิล (Tuples)

ทูเพิลเป็นโครงสร้างข้อมูลที่คล้ายกับลิสต์ แต่มีความแตกต่างสำคัญคือไม่สามารถเปลี่ยนแปลงค่าได้ (immutable) เมื่อสร้างขึ้นมาแล้ว ซึ่งทำให้มีประโยชน์ในหลายสถานการณ์

1. การสร้างทูเพิล:

```python
coordinates = (10, 20)
rgb = (255, 0, 0)
single_item_tuple = (42,)  # ต้องมีจุลภาคเมื่อมีสมาชิกเดียว
empty_tuple = ()
```

2. การเข้าถึงสมาชิกในทูเพิล:

```python
coordinates = (10, 20, 30)
print(coordinates[0])  # 10
print(coordinates[-1])  # 30
print(coordinates[1:3])  # (20, 30)
```

3. การแกะค่าจากทูเพิล (Tuple unpacking):

```python
x, y, z = coordinates
print(x, y, z)  # 10 20 30

# สลับค่าระหว่างตัวแปร
a, b = 5, 10
a, b = b, a
print(a, b)  # 10 5
```

4. การใช้ทูเพิลเป็นคีย์ใน dictionary:

```python
locations = {
    (35.6895, 139.6917): "Tokyo",
    (40.7128, -74.0060): "New York"
}
print(locations[(35.6895, 139.6917)])  # Tokyo
```

5. การวนลูปผ่านทูเพิล:

```python
dimensions = (10, 20, 30)
for dim in dimensions:
    print(dim)

# ผลลัพธ์:
# 10
# 20
# 30
```

6. การใช้ทูเพิลในฟังก์ชัน:

```python
def get_dimensions():
    return (100, 200)

width, height = get_dimensions()
print(f"Width: {width}, Height: {height}")  # Width: 100, Height: 200
```

7. การนับจำนวนสมาชิกในทูเพิล:

```python
numbers = (1, 2, 2, 3, 4, 4, 5)
print(numbers.count(2))  # 2
print(numbers.count(4))  # 2
```

8. การหาตำแหน่งของสมาชิกในทูเพิล:

```python
fruits = ("apple", "banana", "cherry", "banana")
print(fruits.index("banana"))  # 1 (ตำแหน่งแรกที่พบ)
```

9. การแปลงระหว่างลิสต์และทูเพิล:

```python
list_numbers = [1, 2, 3, 4, 5]
tuple_numbers = tuple(list_numbers)
print(tuple_numbers)  # (1, 2, 3, 4, 5)

back_to_list = list(tuple_numbers)
print(back_to_list)  # [1, 2, 3, 4, 5]
```

10. การเปรียบเทียบทูเพิล:

```python
tuple1 = (1, 2, 3)
tuple2 = (1, 2, 3)
tuple3 = (1, 2, 4)

print(tuple1 == tuple2)  # True
print(tuple1 == tuple3)  # False
print(tuple1 < tuple3)   # True (เปรียบเทียบทีละตำแหน่ง)
```

11. การใช้ทูเพิลใน string formatting:

```python
person = ("John", 30)
print("%s is %d years old" % person)  # John is 30 years old
```

12. ทูเพิลซ้อนทูเพิล (Nested tuples):

```python
nested = ((1, 2), (3, 4), (5, 6))
print(nested[1][0])  # 3
```

## 7. เซต (Sets)

เซตเป็นโครงสร้างข้อมูลที่มีลักษณะพิเศษคือไม่มีลำดับและไม่มีสมาชิกซ้ำ ซึ่งมีประโยชน์มากในการจัดการข้อมูลที่ต้องการความเป็นเอกลักษณ์และการดำเนินการทางคณิตศาสตร์เช่น union, intersection เป็นต้น

1. การสร้างเซต:

```python
unique_numbers = {1, 2, 3, 4, 5}
vowels = {'a', 'e', 'i', 'o', 'u'}
empty_set = set()  # ไม่สามารถใช้ {} เพราะจะกลายเป็น dict ว่างเปล่า
```

2. การเพิ่มสมาชิกในเซต:

```python
fruits = {'apple', 'banana', 'cherry'}
fruits.add('orange')
print(fruits)  # {'apple', 'banana', 'cherry', 'orange'}

fruits.update(['grape', 'kiwi'])
print(fruits)  # {'apple', 'banana', 'cherry', 'orange', 'grape', 'kiwi'}
```

3. การลบสมาชิกจากเซต:

```python
fruits = {'apple', 'banana', 'cherry', 'date'}
fruits.remove('banana')  # ถ้าไม่มีสมาชิกนี้จะเกิด KeyError
print(fruits)  # {'apple', 'cherry', 'date'}

fruits.discard('kiwi')  # ไม่เกิด error ถ้าไม่มีสมาชิกนี้
print(fruits)  # {'apple', 'cherry', 'date'}

popped = fruits.pop()  # ลบและคืนค่าสมาชิกแบบสุ่ม
print(popped)  # อาจจะได้ 'apple', 'cherry', หรือ 'date'
print(fruits)  # เหลือสมาชิก 2 ตัวที่เหลือ
```

4. การตรวจสอบสมาชิกในเซต:

```python
fruits = {'apple', 'banana', 'cherry'}
print('banana' in fruits)  # True
print('kiwi' in fruits)    # False
```

5. การดำเนินการทางคณิตศาสตร์กับเซต:

```python
set1 = {1, 2, 3, 4, 5}
set2 = {4, 5, 6, 7, 8}

# Union (รวม)
print(set1 | set2)  # {1, 2, 3, 4, 5, 6, 7, 8}
print(set1.union(set2))  # เหมือนกัน

# Intersection (ส่วนที่เหมือนกัน)
print(set1 & set2)  # {4, 5}
print(set1.intersection(set2))  # เหมือนกัน

# Difference (ส่วนต่าง)
print(set1 - set2)  # {1, 2, 3}
print(set1.difference(set2))  # เหมือนกัน

# Symmetric Difference (ส่วนต่างทั้งสองด้าน)
print(set1 ^ set2)  # {1, 2, 3, 6, 7, 8}
print(set1.symmetric_difference(set2))  # เหมือนกัน
```

6. การตรวจสอบความสัมพันธ์ระหว่างเซต:

```python
set1 = {1, 2, 3}
set2 = {1, 2, 3, 4, 5}
set3 = {6, 7, 8}

print(set1.issubset(set2))    # True
print(set2.issuperset(set1))  # True
print(set1.isdisjoint(set3))  # True (ไม่มีสมาชิกร่วมกันเลย)
```

7. การใช้ List Comprehension กับ Set:

```python
squares = {x**2 for x in range(10)}
print(squares)  # {0, 1, 4, 9, 16, 25, 36, 49, 64, 81}
```

8. การแปลงระหว่างเซตและชนิดข้อมูลอื่น:

```python
# List to Set
my_list = [1, 2, 2, 3, 4, 4, 5]
my_set = set(my_list)
print(my_set)  # {1, 2, 3, 4, 5}

# Set to List
back_to_list = list(my_set)
print(back_to_list)  # [1, 2, 3, 4, 5] (ลำดับอาจไม่เหมือนเดิม)

# String to Set
my_string = "hello"
char_set = set(my_string)
print(char_set)  # {'h', 'e', 'l', 'o'}
```

9. การใช้เซตในการกำจัดข้อมูลซ้ำ:

```python
numbers = [1, 2, 2, 3, 3, 3, 4, 4, 5]
unique_numbers = list(set(numbers))
print(unique_numbers)  # [1, 2, 3, 4, 5]
```

10. เซตแบบ Frozen (Immutable):

```python
frozen = frozenset([1, 2, 3, 4, 5])
# frozen.add(6)  # จะเกิด AttributeError เพราะไม่สามารถแก้ไขได้
```

## 8. ดิกชันนารี (Dictionaries)

ดิกชันนารีเป็นโครงสร้างข้อมูลที่เก็บข้อมูลในรูปแบบคู่ key-value โดยที่ key ต้องไม่ซ้ำกันและไม่สามารถเปลี่ยนแปลงได้ (immutable) ส่วน value สามารถเป็นข้อมูลประเภทใดก็ได้และสามารถเปลี่ยนแปลงได้

1. การสร้างดิกชันนารี:

```python
person = {"name": "John", "age": 30, "city": "New York"}
empty_dict = {}
dict_constructor = dict(name="Alice", age=25, city="London")
```

2. การเข้าถึงและแก้ไขข้อมูล:

```python
person = {"name": "John", "age": 30, "city": "New York"}
print(person["name"])  # John

person["age"] = 31
person["job"] = "Engineer"
print(person)  # {'name': 'John', 'age': 31, 'city': 'New York', 'job': 'Engineer'}
```

3. การใช้เมธอด get() เพื่อป้องกัน KeyError:

```python
print(person.get("salary", "Not specified"))  # Not specified
```

4. การลบข้อมูล:

```python
del person["job"]
removed_value = person.pop("age")
print(removed_value)  # 31
print(person)  # {'name': 'John', 'city': 'New York'}
```

5. การวนลูปผ่านดิกชันนารี:

```python
for key in person:
    print(f"{key}: {person[key]}")

for key, value in person.items():
    print(f"{key}: {value}")

print(person.keys())    # dict_keys(['name', 'city'])
print(person.values())  # dict_values(['John', 'New York'])
```

6. การตรวจสอบ key:

```python
print("name" in person)  # True
print("age" in person)   # False
```

7. Dictionary Comprehension:

```python
squares = {x: x**2 for x in range(5)}
print(squares)  # {0: 0, 1: 1, 2: 4, 3: 9, 4: 16}
```

8. การรวมดิกชันนารี:

```python
dict1 = {"a": 1, "b": 2}
dict2 = {"c": 3, "d": 4}
merged = {**dict1, **dict2}
print(merged)  # {'a': 1, 'b': 2, 'c': 3, 'd': 4}

# หรือใช้ update() method
dict1.update(dict2)
print(dict1)  # {'a': 1, 'b': 2, 'c': 3, 'd': 4}
```

9. Nested Dictionaries:

```python
employees = {
    "John": {"age": 30, "position": "Manager"},
    "Alice": {"age": 25, "position": "Developer"}
}
print(employees["John"]["position"])  # Manager
```

10. การใช้ defaultdict:

```python
from collections import defaultdict

fruit_counts = defaultdict(int)
fruits = ["apple", "banana", "apple", "cherry", "banana", "apple"]

for fruit in fruits:
    fruit_counts[fruit] += 1

print(dict(fruit_counts))  # {'apple': 3, 'banana': 2, 'cherry': 1}
```

11. การใช้ OrderedDict (ตั้งแต่ Python 3.7 ดิกชันนารีปกติก็เก็บลำดับแล้ว):

```python
from collections import OrderedDict

ordered = OrderedDict()
ordered["a"] = 1
ordered["b"] = 2
ordered["c"] = 3

print(ordered)  # OrderedDict([('a', 1), ('b', 2), ('c', 3)])
```

12. การใช้ dict() constructor กับ zip():

```python
keys = ["name", "age", "city"]
values = ["John", 30, "New York"]
person = dict(zip(keys, values))
print(person)  # {'name': 'John', 'age': 30, 'city': 'New York'}
```

13. การใช้ setdefault():

```python
person = {"name": "John", "age": 30}
person.setdefault("city", "Unknown")
print(person)  # {'name': 'John', 'age': 30, 'city': 'Unknown'}
```

## 9. NoneType

NoneType เป็นชนิดข้อมูลพิเศษใน Python ที่มีค่าเพียงค่าเดียวคือ None ซึ่งใช้เพื่อแสดงถึงการไม่มีค่าหรือการไม่มีอะไรเลย มีประโยชน์มากในการเขียนโปรแกรมเพื่อระบุสถานะพิเศษ หรือค่าเริ่มต้นที่ยังไม่ได้กำหนด

1. การกำหนดค่า None:

```python
result = None
print(result)  # None
print(type(result))  # <class 'NoneType'>
```

2. การใช้ None ในเงื่อนไข:

```python
def find_user(username):
    # สมมติว่าเป็นฟังก์ชันค้นหาผู้ใช้ในฐานข้อมูล
    if username == "admin":
        return {"name": "Admin", "role": "administrator"}
    return None

user = find_user("guest")
if user is None:
    print("User not found")
else:
    print(f"Welcome, {user['name']}")

# ผลลัพธ์: User not found
```

3. การใช้ None เป็นค่าเริ่มต้นของพารามิเตอร์:

```python
def greet(name=None):
    if name is None:
        return "Hello, Guest!"
    return f"Hello, {name}!"

print(greet())  # Hello, Guest!
print(greet("Alice"))  # Hello, Alice!
```

4. การเปรียบเทียบกับ None:

```python
# วิธีที่แนะนำ
x = None
if x is None:
    print("x is None")

# ไม่แนะนำให้ใช้ ==
if x == None:
    print("x equals None")
```

5. การใช้ None ในลิสต์:

```python
values = [1, None, 3, None, 5]
cleaned_values = [v for v in values if v is not None]
print(cleaned_values)  # [1, 3, 5]
```

6. การใช้ None กับ dictionary:

```python
user_prefs = {"theme": "dark", "font_size": None, "language": "en"}
font_size = user_prefs.get("font_size", "default")
print(font_size)  # default
```

7. การใช้ None ในการส่งคืนค่าจากฟังก์ชัน:

```python
def divide(a, b):
    if b == 0:
        return None
    return a / b

result = divide(10, 2)
if result is not None:
    print(f"Result: {result}")
else:
    print("Cannot divide by zero")

# ผลลัพธ์: Result: 5.0
```

8. การใช้ None ใน try-except:

```python
def safe_int_convert(value):
    try:
        return int(value)
    except ValueError:
        return None

print(safe_int_convert("123"))  # 123
print(safe_int_convert("abc"))  # None
```

9. การใช้ None ในการตรวจสอบว่าตัวแปรได้รับการกำหนดค่าหรือยัง:

```python
def process_data(data=None):
    if data is None:
        data = []
    # ดำเนินการกับข้อมูล
    return len(data)

print(process_data())  # 0
print(process_data([1, 2, 3]))  # 3
```

10. การใช้ None ในการเปรียบเทียบหลายค่า:

```python
def check_all_none(*args):
    return all(arg is None for arg in args)

print(check_all_none(None, None, None))  # True
print(check_all_none(None, 1, None))  # False
```

### การตรวจสอบประเภทข้อมูล

คุณสามารถใช้ฟังก์ชัน `type()` เพื่อตรวจสอบประเภทของตัวแปร:

```python
x = 5
print(type(x))  # <class 'int'>

name = "Alice"
print(type(name))  # <class 'str'>
```

### การแปลงประเภทข้อมูล

Python อนุญาตให้แปลงระหว่างประเภทข้อมูลต่างๆ ได้:

```python
# แปลงเป็นจำนวนเต็ม
x = int("10")  # x = 10

# แปลงเป็นทศนิยม
y = float("3.14")  # y = 3.14

# แปลงเป็นสตริง
z = str(42)  # z = "42"

# แปลงเป็นลิสต์
my_list = list("Hello")  # my_list = ['H', 'e', 'l', 'l', 'o']
```

ตัวอย่างการใช้งาน:

```python
# ตัวอย่างการใช้ตัวแปรและประเภทข้อมูลต่างๆ
name = "Alice"
age = 30
height = 1.65
is_student = False
hobbies = ["reading", "swimming", "coding"]
address = ("123 Main St", "City", "12345")
grades = {"math": 90, "science": 85, "history": 88}

print(f"Name: {name}")
print(f"Age: {age}")
print(f"Height: {height} meters")
print(f"Is student? {is_student}")
print(f"Hobbies: {', '.join(hobbies)}")
print(f"Address: {', '.join(address)}")
print("Grades:")
for subject, grade in grades.items():
    print(f"  {subject}: {grade}")
```

ผลลัพธ์:

```
Name: Alice
Age: 30
Height: 1.65 meters
Is student? False
Hobbies: reading, swimming, coding
Address: 123 Main St, City, 12345
Grades:
  math: 90
  science: 85
  history: 88
```
