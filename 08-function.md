# ฟังก์ชัน

## 1. การสร้างและเรียกใช้ฟังก์ชัน

ฟังก์ชันใน Python สร้างโดยใช้คีย์เวิร์ด `def` ตามด้วยชื่อฟังก์ชันและวงเล็บที่อาจมีพารามิเตอร์:

```python
def greet():
    print("สวัสดีครับ!")

# เรียกใช้ฟังก์ชัน
greet()  # ผลลัพธ์: สวัสดีครับ!
```

## 2. พารามิเตอร์และการส่งค่ากลับ

a. ฟังก์ชันที่มีพารามิเตอร์:

```python
def greet_person(name):
    print(f"สวัสดีคุณ {name}")

greet_person("สมชาย")  # ผลลัพธ์: สวัสดีคุณสมชาย
```

b. ฟังก์ชันที่ส่งค่ากลับ:

```python
def add(a, b):
    return a + b

result = add(5, 3)
print(result)  # ผลลัพธ์: 8
```

c. ฟังก์ชันที่มีค่าเริ่มต้นของพารามิเตอร์:

```python
def greet_with_title(name, title="คุณ"):
    print(f"สวัสดี{title}{name}")

greet_with_title("สมชาย")  # ผลลัพธ์: สวัสดีคุณสมชาย
greet_with_title("สมศรี", "คุณหมอ")  # ผลลัพธ์: สวัสดีคุณหมอสมศรี
```

d. ฟังก์ชันที่รับจำนวนพารามิเตอร์ไม่จำกัด:

```python
def sum_all(*args):
    return sum(args)

print(sum_all(1, 2, 3, 4))  # ผลลัพธ์: 10
print(sum_all(10, 20))  # ผลลัพธ์: 30
```

e. ฟังก์ชันที่รับคีย์เวิร์ดอาร์กิวเมนต์:

```python
def print_info(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")

print_info(name="สมชาย", age=30, city="กรุงเทพ")
# ผลลัพธ์:
# name: สมชาย
# age: 30
# city: กรุงเทพ
```

## 3. การประยุกต์ใช้ฟังก์ชัน

a. ฟังก์ชันเป็นออบเจ็กต์ชั้นหนึ่ง (First-class objects):

```python
def multiply_by(n):
    def multiplier(x):
        return x * n
    return multiplier

double = multiply_by(2)
triple = multiply_by(3)

print(double(5))  # ผลลัพธ์: 10
print(triple(5))  # ผลลัพธ์: 15
```

b. การใช้ lambda functions:

```python
square = lambda x: x ** 2
print(square(5))  # ผลลัพธ์: 25

# ใช้กับ built-in functions
numbers = [1, 2, 3, 4, 5]
squared_numbers = list(map(lambda x: x ** 2, numbers))
print(squared_numbers)  # ผลลัพธ์: [1, 4, 9, 16, 25]
```

c. การใช้ฟังก์ชันกับ list comprehension:

```python
def is_even(n):
    return n % 2 == 0

numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
even_numbers = [n for n in numbers if is_even(n)]
print(even_numbers)  # ผลลัพธ์: [2, 4, 6, 8, 10]
```

## 4. ตัวอย่างการประยุกต์ใช้ฟังก์ชัน

โจทย์: สร้างโปรแกรมจัดการรายการสินค้าในร้านค้า โดยใช้ฟังก์ชันในการจัดการการเพิ่ม, ลบ, แสดง และคำนวณราคารวมของสินค้า

```python
# สร้างรายการสินค้าเริ่มต้น
inventory = {}

def add_item(name, price, quantity):
    if name in inventory:
        print(f"สินค้า '{name}' มีอยู่แล้ว ทำการอัพเดตจำนวน")
        inventory[name]['quantity'] += quantity
    else:
        inventory[name] = {'price': price, 'quantity': quantity}
    print(f"เพิ่มสินค้า '{name}' จำนวน {quantity} ชิ้น ราคาชิ้นละ {price} บาท")

def remove_item(name, quantity):
    if name in inventory:
        if inventory[name]['quantity'] >= quantity:
            inventory[name]['quantity'] -= quantity
            print(f"ลบสินค้า '{name}' จำนวน {quantity} ชิ้น")
            if inventory[name]['quantity'] == 0:
                del inventory[name]
                print(f"สินค้า '{name}' ถูกลบออกจากรายการเนื่องจากหมดสต็อก")
        else:
            print(f"ไม่สามารถลบสินค้า '{name}' ได้ เนื่องจากมีจำนวนไม่เพียงพอ")
    else:
        print(f"ไม่พบสินค้า '{name}' ในรายการ")

def display_inventory():
    if not inventory:
        print("ไม่มีสินค้าในรายการ")
    else:
        print("รายการสินค้า:")
        for name, info in inventory.items():
            print(f"- {name}: ราคา {info['price']} บาท, จำนวน {info['quantity']} ชิ้น")

def calculate_total_value():
    total = sum(item['price'] * item['quantity'] for item in inventory.values())
    return total

# ทดสอบการใช้งานฟังก์ชัน
add_item("แอปเปิ้ล", 10, 50)
add_item("กล้วย", 5, 100)
add_item("ส้ม", 8, 75)

display_inventory()

remove_item("แอปเปิ้ล", 20)
add_item("แอปเปิ้ล", 12, 30)

display_inventory()

total_value = calculate_total_value()
print(f"มูลค่ารวมของสินค้าทั้งหมด: {total_value} บาท")
```

ในตัวอย่างนี้ เราได้สร้างฟังก์ชันต่างๆ เพื่อจัดการกับรายการสินค้า:

- `add_item()`: เพิ่มสินค้าใหม่หรืออัพเดตจำนวนสินค้าที่มีอยู่
- `remove_item()`: ลบสินค้าออกจากรายการหรือลดจำนวนสินค้า
- `display_inventory()`: แสดงรายการสินค้าทั้งหมด
- `calculate_total_value()`: คำนวณมูลค่ารวมของสินค้าทั้งหมด

การใช้ฟังก์ชันช่วยให้โค้ดมีโครงสร้างที่ดี อ่านง่าย และสามารถนำกลับมาใช้ซ้ำได้ ซึ่งเป็นหลักการสำคัญในการเขียนโปรแกรมเชิงฟังก์ชัน (Functional Programming)
