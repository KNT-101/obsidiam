
ဒီ code ထဲမှာ `couplenums` ဟာ **set comprehension** ကို သုံးပြီး **nested loop** လုပ်နေတာပါ။  
ဒီလိုနဲ့ **(x, y) pair** တွေကို set အနေနဲ့ ထုတ်ယူထားပါတယ်။  

---

## **Code Breakdown**
```python
couplenums = {(x, y) for x in range(3) for y in range(2)}
print(couplenums)
```

### **Step-by-step Execution**
#### **1️⃣ Outer loop (`for x in range(3)`)**
```python
for x in range(3):
```
➡️ `x` က **0, 1, 2** ဆိုပြီး **၃ ခါ** loop ပတ်မယ်။  

#### **2️⃣ Inner loop (`for y in range(2)`)**
```python
for y in range(2):
```
➡️ `y` က **0, 1** ဆိုပြီး **၂ ခါ** loop ပတ်မယ်။  

➡️ `y` loop ဟာ **x loop အတွင်းမှာရှိတဲ့ nested loop** ဖြစ်တဲ့အတွက် **x တစ်ခုစီအတွက် y ကို 0, 1** ထိယူမယ်။  

#### **3️⃣ Set Comprehension မှာ Pair (x, y) ကို add**
```python
{(x, y) for x in range(3) for y in range(2)}
```
➡️ (x, y) ကို set ထဲ ထည့်မယ်။  
➡️ **Set ဖြစ်တဲ့အတွက် unique values** ကိုသာ သိမ်းမယ်။  

---

## **Nested Loop Detail Explanation**
ဒီ code ကို normal nested loop လိုပြန်ရေးရင်  
```python
couplenums = set()

for x in range(3):  # x → 0, 1, 2
    for y in range(2):  # y → 0, 1
        couplenums.add((x, y))  # (x, y) pair တွေထည့်မယ်

print(couplenums)
```
💡 **Flow ကို နားလည်ဖို့ Table နဲ့ ပြမယ်။**  

| `x` Value | `y` Value | `(x, y)` Pair |
|-----------|-----------|-------------|
| 0 | 0 | (0, 0) |
| 0 | 1 | (0, 1) |
| 1 | 0 | (1, 0) |
| 1 | 1 | (1, 1) |
| 2 | 0 | (2, 0) |
| 2 | 1 | (2, 1) |

---
## **Code Execution Flow**
 **Nested Loop ကို Manual Execution လုပ်ကြည့်မယ်။**

### **1️⃣ x = 0**
- `y = 0` → `(0, 0)`
- `y = 1` → `(0, 1)`

### **2️⃣ x = 1**
- `y = 0` → `(1, 0)`
- `y = 1` → `(1, 1)`

### **3️⃣ x = 2**
- `y = 0` → `(2, 0)`
- `y = 1` → `(2, 1)`

### **Final Output**
```python
{(0, 1), (2, 1), (0, 0), (1, 1), (2, 0), (1, 0)}
```
➡️ Set မှာတော့ **order guarantee မရှိဘူး**  
➡️ **တူညီတဲ့ values မဖြစ်ရင်တော့ order က random ဖြစ်နိုင်တယ်။**

---
## **Nested Loop Structure Summary**
```python
for outer_variable in outer_range:
    for inner_variable in inner_range:
        # Code execution
```
👉 **Outer loop** တစ်ခါသွားရင် **Inner loop** အကုန်ပြုလုပ်တယ်။  
👉 **Inner loop ပြီးရင်မှ Outer loop value အသစ် ပြောင်းမယ်။**

---

## **Example 2: Nested Loop**
💡 **Example**  
```python
for i in range(2):
    for j in range(3):
        print(f"({i}, {j})", end=" ")
    print()  # Newline
```
### **Output**
```
(0, 0) (0, 1) (0, 2) 
(1, 0) (1, 1) (1, 2)
```
🔥 **Explanation**  
- `i = 0` ရဲ့ အတွင်းမှာ `j = 0, 1, 2` ကို loop ပတ်တယ်  
- `i = 1` ရဲ့ အတွင်းမှာ `j = 0, 1, 2` ကို loop ပတ်တယ်  

---

## **Example 3: Nested Loop with List Comprehension**
```python
pairs = [(x, y) for x in range(2) for y in range(3)]
print(pairs)
```
### **Output**
```
[(0, 0), (0, 1), (0, 2), (1, 0), (1, 1), (1, 2)]
```
🔥 **Set Comprehension နဲ့ ခြားတာက**  
👉 **Set `{}` သုံးရင် unique values only**  
👉 **List `[]` သုံးရင် original order ထားနိုင်တယ်**

---

## **Summary**
✔️ **Nested Loop** က **Outer Loop တစ်ခါသွားတိုင်း Inner Loop အကုန်လုပ်**  
✔️ **Set Comprehension** ကို `{}` သုံးပြီး Set ထဲထည့်နိုင်  
✔️ **List Comprehension** နဲ့လည်း လိုချင်တဲ့ data ကို လုပ်နိုင်  
✔️ **Loop ပတ်တာကို Table သုံးပြီး လေ့လာဖို့အရေးကြီး**

---

## **🔹 Set `{}` နဲ့ List `[]` တို့ရဲ့ Key Differences**
| Feature | **Set `{}`** | **List `[]`** |
|---------|-------------|--------------|
| **Order (စီပုံ)** | **No order (unordered)** | **Ordered (စီထားနိုင်)** |
| **Duplicates (တူညီမှု)** | **No duplicates (unique values only)** | **Allows duplicates** |
| **Indexing** | **No indexing (No position access)** | **Indexing supported (list[0], list[1])** |
| **Performance** | **Faster for lookups (`O(1)`)** | **Slower for lookups (`O(n)`)** |
| **Mutable?** | **Mutable (တန်ဖိုးပြောင်းလို့ရ)** | **Mutable (တန်ဖိုးပြောင်းလို့ရ)** |

---

###  **Example 1: Set `{}` Removes Duplicates & Is Unordered**


```python
my_set = {3, 1, 2, 3, 1, 4}
print(my_set)
```
### **Output**
```
{1, 2, 3, 4}
```
✔ **Order မရှိဘူး** (အလိုလို အစီအစဉ်မဟုတ်)  
✔ **Duplicate (3, 1) ကို တစ်ခုပဲထားလိုက်တယ်**  

---

### **Example 2: List `[]` Maintains Order & Allows Duplicates**

```python
my_list = [3, 1, 2, 3, 1, 4]
print(my_list)
```
### **Output**
```
[3, 1, 2, 3, 1, 4]
```
✔ **Order ကို တိတိကျကျ ထားနိုင်တယ်**  
✔ **Duplicates (3, 1) တူနေတာတွေကို လက်ခံတယ်**  

---

## **Example 3: Set vs List in Loops**
```python
data = [1, 2, 3, 2, 4, 1, 5]

print("Set:", {x for x in data})  # Removes Duplicates
print("List:", [x for x in data])  # Keeps Order
```
### **Output**
```
Set: {1, 2, 3, 4, 5}  # No Order, No Duplicates
List: [1, 2, 3, 2, 4, 1, 5]  # Ordered, Keeps Duplicates
```

---

## **Example 4: Checking Membership Performance**
```python
my_list = [x for x in range(1000000)]
my_set = {x for x in range(1000000)}

# Checking if 999999 is in list
import time
start = time.time()
print(999999 in my_list)
print("List Lookup Time:", time.time() - start)

# Checking if 999999 is in set
start = time.time()
print(999999 in my_set)
print("Set Lookup Time:", time.time() - start)
```
### **Results**
✔ **Set lookup is faster (`O(1)`)**  
✔ **List lookup is slower (`O(n)`)**  

---

## **Conclusion**

- ✅ **Set `{}`** → **Unique values, Unordered, Fast lookups**  
- ✅ **List `[]`** → **Maintains order, Allows duplicates, Supports indexing**  

---

