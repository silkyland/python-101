# "Hello, World!"

1. เปิด Visual Studio Code:
   - เปิดโปรแกรม VS Code ที่คุณได้ติดตั้งไว้

2. สร้างไฟล์ใหม่:
   - คลิกที่ไอคอน "New File" (มักอยู่ที่มุมซ้ายบน) หรือใช้ shortcut Ctrl+N (Windows/Linux) หรือ Cmd+N (macOS)
   - บันทึกไฟล์โดยกด Ctrl+S (Windows/Linux) หรือ Cmd+S (macOS)
   - ตั้งชื่อไฟล์เป็น "hello_world.py" และเลือกตำแหน่งที่ต้องการบันทึก

3. เขียนโค้ด:
   - ในไฟล์ที่เพิ่งสร้าง พิมพ์โค้ดต่อไปนี้:

   ```python
   print("Hello, World!")
   ```

4. รันโปรแกรม:
   มีหลายวิธีในการรันโปรแกรม Python ใน VS Code:

   a. ใช้ปุ่ม Run:
      - มองหาปุ่มสามเหลี่ยมสีเขียว (Play button) ที่มุมขวาบนของ VS Code
      - คลิกที่ปุ่มนี้เพื่อรันโปรแกรม

   b. ใช้ Terminal ใน VS Code:
      - เปิด Terminal ใน VS Code โดยไปที่ Terminal > New Terminal ในเมนูด้านบน หรือใช้ shortcut Ctrl+` (backtick)
      - ใน Terminal พิมพ์คำสั่ง:

        ```
        python hello_world.py
        ```

      - กด Enter เพื่อรันโปรแกรม

   c. ใช้ Code Runner extension (ถ้าติดตั้งไว้):
      - คลิกขวาที่หน้าต่างโค้ด
      - เลือก "Run Code" จากเมนูที่ปรากฏ

5. ดูผลลัพธ์:
   - หลังจากรันโปรแกรม คุณควรเห็นข้อความ "Hello, World!" ปรากฏในหน้าต่าง Terminal หรือ Output ของ VS Code

6. ทดสอบเพิ่มเติม:
   เพื่อให้แน่ใจว่าทุกอย่างทำงานได้ถูกต้อง คุณอาจลองเขียนโค้ดที่ซับซ้อนขึ้นเล็กน้อย เช่น:

   ```python
   name = input("What's your name? ")
   print(f"Hello, {name}! Welcome to Python programming.")
   ```

   โค้ดนี้จะขอให้ผู้ใช้ป้อนชื่อ และจากนั้นจะแสดงข้อความทักทายพร้อมชื่อที่ป้อน

7. ตรวจสอบ Python Extension:
   - หากคุณเห็นไฮไลท์สีของโค้ด (syntax highlighting) และ IntelliSense (การแนะนำโค้ดอัตโนมัติ) ทำงาน แสดงว่า Python Extension ใน VS Code ทำงานได้อย่างถูกต้อง

8. ตรวจสอบ Python Interpreter:
   - มองไปที่มุมล่างซ้ายของ VS Code คุณควรเห็นเวอร์ชันของ Python ที่กำลังใช้งาน
   - หากไม่เห็น หรือเห็นเวอร์ชันที่ไม่ถูกต้อง ให้คลิกที่ตำแหน่งนั้นและเลือก Python Interpreter ที่ถูกต้อง
