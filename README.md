## แบบฝึกหัดที่ 1
#### จงเขียนโปรแกรมคำนวน Factorial number ในรูปแบบ Recursive function และจงทดสอบ 15! มีค่าเท่าไหร่ 
```python
def factorial(n):
    if n == 0:
        return 1
    return n * factorial(n-1)

# ทดสอบคำนวณ 15!
number = 15
result = factorial(number)
print(f"{number}! = {result}")
```

#### จงเขียนโปรแกรมคำนวณจำนวนนิสิตคงเหลือในรูปแบบ Recursive realation โดยกำหนดให้ปีที่ 1 รับนิสิตจำนวน 100 คน และมีอัตรานิสิตลาออกเท่ากับ 10% (x = 0.9) จงทดสอบว่า ณ ปีที่ 5 จะเหลือนิสิตประมาณกี่คน
```python
def remaining_students(n, x=0.9):
    # ถ้าปีแรก ให้ส่งคืนจำนวน 100 คน
    if n == 1:
        return 100
    # คำนวณจำนวนนิสิตที่เหลือในแต่ละปี โดยลดลงตามอัตรา x
    return int(remaining_students(n - 1, x) * x)

# ทดสอบคำนวณจำนวนนิสิตคงเหลือในปีที่ 5
year = 5
result = remaining_students(year)
print(f"จำนวนนิสิตคงเหลือ ณ ปีที่ {year} = {result} คน")
```
## แบบฝึกหัดที่ 2
#### 1. ฟังก์ชัน discount รับค่าอาร์กิวเมนท์สองค่า เป็นจำนวนเงิน (x) และเปอร์เซ็๋นต์ส่วนลด (y) ให้คำนวณหาส่วนลดที่คำนวณได้แล้วส่งผลลัพธ์กลับ
```python
money = [500, 1000, 300, 800]

# lambda function สำหรับคำนวณส่วนลด
discount = lambda x, y: x * (1 - y / 100)

# ทดสอบการใช้ฟังก์ชัน discount
result = [discount(m, 10) for m in money]
print(f"ราคาหลังจากส่วนลด 10%: {result}") # ราคาหลังจากส่วนลด 10%: [450.0, 900.0, 270.0, 720.0]
```

#### 2. ฟังก์ชัน checknumber รับค่าอาร์กิวเม้นท์ (x) ให้ตรวจสอบว่าเป็นค่าตัวเลขหรือไม่ ถ้าใช่ ให้ส่งผลลัพธ์เป็น 1 และถ้าไม่ใช่ให้ส่งผลลัพธ์เป็น 0
```python
money = [500, 1000, 300, 800]

# lambda function สำหรับตรวจสอบว่าค่าเป็นตัวเลขหรือไม่
checknumber = lambda x: 1 if isinstance(x, (int, float)) else 0
result = [checknumber(value) for value in test_values]
print(result) # [1, 1, 1, 1]
```

#### 3. ฟังก์ชัน calDiscount รับค่าอาร์กิวเมนท์ที่ส่งเข้ามากกว่า 500 บาทให้ส่วนลด 10% และน้อยกว่า 500 บาท ให้ส่วนลด 5% แล้วส่งเป็นผลลัพธ์ส่วนลดกลับ
```python
money = [500, 1000, 300, 800]

# lambda function สำหรับคำนวณส่วนลดตามเงื่อนไข
calDiscount = lambda x: x * 0.9 if x > 500 else x * 0.95

# ทดสอบการใช้ฟังก์ชัน calDiscount
result = [calDiscount(m) for m in money]
print(f"ราคาหลังจากส่วนลด: {result}") # ราคาหลังจากส่วนลด: [475.0, 900.0, 285.0, 720.0]
```

#### 4. ฟังก์ชัน calVAT รับค่าจากรายการใน money ให้เพิ่มค่าเป็น 1.07 เท่าค่าเดิมแล้วส่งผลลัพธ์กลับ
```python
money = [500, 1000, 300, 800]

# lambda function สำหรับคำนวณภาษี VAT (เพิ่ม 7%)
calVAT = lambda x: x * 1.07

# ทดสอบการใช้ฟังก์ชัน calVAT
result = [calVAT(m) for m in money]
print(f"ราคาหลังจากรวม VAT 7%: {result}")
```
## แบบฝึกหัดที่ 3
#### สร้าง filter ที่สามารถในคำตอบดังต่อไปนี้ เมื่อ ตัวแปร A,B เป็น list และ X เป็น dictionary ที่มีรายการค่าดังต่อไปนี้
A = [1, 6, 7, 3, 5, 8]
B = [2, 5, 7, 4, 6, 'A']
X = {'Alan': 100, 'Bob': 75, 'Clark': 60, 'David': 55}

```python
# Output -> C = [6, 7, 8]
C = list(filter(lambda x: (x == 6 or x == 7 or x == 8), A))
print(C)  # [6, 7, 8]
```

```python
# Output -> C = [1, 7, 3, 5]
C = list(filter(lambda x: (x % 2 != 0), A))
print(C)  # [1, 7, 3, 5]
```

```python
# Output -> C = ['A']
C = list(filter(lambda x: (x == 'A'), B))
print(C)  # ['A']
```

```python
# Output -> C = ['Alan', 'Bob']
C = list(filter(lambda key: X[key] >= 75, X))
print(C)  # ['Alan', 'Bob']
```
## แบบฝึกหัดที่ 4
#### สร้าง map และ reduce ที่สามารถหาคำตอบดังต่อไปนี้ เมื่อตัวแปร A, B เป็น list ที่มีรายการค่าดังต่อไปนี้
A = [1, 2, 3, 4, 5]
B = [2, 4, 6, 8, 10]

```python
# Output -> C = [15] (sum of A)
C = [reduce(lambda x, y: x + y, A)]
print(C)  # [15]
```
```python
# Output -> C = [10] (sum of even numbers in A)
C = [reduce(lambda x, y: x + y, filter(lambda x: x % 2 == 0, A))]
print(C)  # [10]
```
```python
# Output -> C = [3, 6, 9, 12, 15] (A multiplied by 3)
C = list(map(lambda x: x * 3, A))
print(C)  # [3, 6, 9, 12, 15]
```
```python
# Output -> C = [0, 4, 0, 8, 0] (A elements: if even keep them, if odd set to 0)
C = list(map(lambda x: x if x % 2 == 0 else 0, A))
print(C)  # [0, 4, 0, 8, 0]
```
