# การดำเนินการทางคณิตศาสตร์ใน Python

1. ตัวดำเนินการพื้นฐาน (Basic Operators):

   - บวก (+):

     ```python
     a = 5 + 3  # a = 8
     ```

   - ลบ (-):

     ```python
     b = 10 - 4  # b = 6
     ```

   - คูณ (*):

     ```python
     c = 3 * 4  # c = 12
     ```

   - หาร (/):

     ```python
     d = 20 / 5  # d = 4.0 (ผลลัพธ์เป็นทศนิยมเสมอ)
     ```

   - หารแบบปัดเศษลง (//):

     ```python
     e = 17 // 5  # e = 3
     ```

   - หารเอาเศษ (%):

     ```python
     f = 17 % 5  # f = 2
     ```

   - ยกกำลัง (**):

     ```python
     g = 2 ** 3  # g = 8
     ```

2. ลำดับการดำเนินการ (Order of Operations):
   Python ใช้ลำดับการดำเนินการตามหลัก PEMDAS (Parentheses, Exponents, Multiplication/Division, Addition/Subtraction)

   ```python
   result = 2 + 3 * 4  # result = 14
   result = (2 + 3) * 4  # result = 20
   ```

3. การดำเนินการกับตัวแปร:

   ```python
   x = 10
   y = 5
   sum = x + y  # sum = 15
   difference = x - y  # difference = 5
   product = x * y  # product = 50
   quotient = x / y  # quotient = 2.0
   ```

4. ตัวดำเนินการกำหนดค่าแบบย่อ (Compound Assignment Operators):

   ```python
   x = 10
   x += 5  # เท่ากับ x = x + 5, x จะมีค่าเป็น 15
   x -= 3  # x = 12
   x *= 2  # x = 24
   x /= 4  # x = 6.0
   x //= 2  # x = 3.0
   x %= 2  # x = 1.0
   x **= 3  # x = 1.0
   ```

5. ฟังก์ชันทางคณิตศาสตร์จากโมดูล math:

   ```python
   import math

   # ค่าสัมบูรณ์
   abs_value = abs(-5)  # abs_value = 5

   # ปัดเศษขึ้น
   ceiling = math.ceil(4.3)  # ceiling = 5

   # ปัดเศษลง
   floor = math.floor(4.7)  # floor = 4

   # ปัดเศษ
   rounded = round(4.5)  # rounded = 5

   # ค่า pi
   pi_value = math.pi  # pi_value ≈ 3.141592653589793

   # ฟังก์ชันตรีโกณมิติ
   sin_value = math.sin(math.pi/2)  # sin_value = 1.0

   # ลอการิทึม
   log_value = math.log(100, 10)  # log_value = 2.0

   # รากที่สอง
   sqrt_value = math.sqrt(16)  # sqrt_value = 4.0
   ```

6. การดำเนินการกับตัวเลขจำนวนเชิงซ้อน:

   ```python
   a = 2 + 3j
   b = 1 - 2j
   sum_complex = a + b  # (3+1j)
   product_complex = a * b  # (8-1j)
   ```

7. การแปลงระหว่างระบบเลขฐาน:

   ```python
   # แปลงเลขฐาน 2 เป็นฐาน 10
   binary_to_decimal = int('1010', 2)  # 10

   # แปลงเลขฐาน 10 เป็นฐาน 2
   decimal_to_binary = bin(10)  # '0b1010'

   # แปลงเลขฐาน 16 เป็นฐาน 10
   hex_to_decimal = int('A', 16)  # 10

   # แปลงเลขฐาน 10 เป็นฐาน 16
   decimal_to_hex = hex(10)  # '0xa'
   ```

8. การจัดการกับความแม่นยำของทศนิยม:

   ```python
   from decimal import Decimal

   a = Decimal('0.1')
   b = Decimal('0.2')
   c = a + b  # Decimal('0.3') (แม่นยำกว่าการใช้ float)
   ```

9. ตัวอย่างการใช้งานในสถานการณ์จริง:

   ```python
   # คำนวณพื้นที่วงกลม
   radius = 5
   area = math.pi * radius ** 2
   print(f"พื้นที่วงกลมรัศมี {radius} คือ {area:.2f}")

   # คำนวณดอกเบี้ยทบต้น
   principal = 1000  # เงินต้น
   rate = 0.05  # อัตราดอกเบี้ย 5%
   time = 5  # ระยะเวลา 5 ปี
   amount = principal * (1 + rate) ** time
   print(f"เงิน {principal} บาท ที่ดอกเบี้ย {rate*100}% เป็นเวลา {time} ปี จะเพิ่มเป็น {amount:.2f} บาท")
   ```

การดำเนินการทางคณิตศาสตร์ใน Python มีความยืดหยุ่นและมีประสิทธิภาพ คุณสามารถใช้ตัวดำเนินการพื้นฐานสำหรับการคำนวณทั่วไป และใช้ฟังก์ชันจากโมดูล `math` สำหรับการคำนวณที่ซับซ้อนขึ้น นอกจากนี้ การใช้ `Decimal` ช่วยให้คุณจัดการกับการคำนวณที่ต้องการความแม่นยำสูง เช่น ในด้านการเงิน
