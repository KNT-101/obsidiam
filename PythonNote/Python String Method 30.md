
## **1. `capitalize()`**  
String ရဲ့ ပထမစာလုံးကို **မြှောက်ရေး** (`Uppercase`) ပြုလုပ်ပေးမယ်။  

```python
text = "hello world"
print(text.capitalize())  
```
**Output:**  
```text
Hello world
```

---

## **2. `upper()` & `lower()`**  
- `upper()` → **လုံးဝ Capitalized** ဖြစ်အောင်ပြောင်းမယ်။  
- `lower()` → **လုံးဝ သေးလုံး** ဖြစ်အောင်ပြောင်းမယ်။  

```python
text = "Python Programming"
print(text.upper())  
print(text.lower())  
```
**Output:**  
```text
PYTHON PROGRAMMING
python programming
```

---

## **3. `title()`**  
စာလုံးတိုင်း **Capitalized** ဖြစ်အောင်ပြောင်းမယ်။  

```python
text = "python programming language"
print(text.title())  
```
**Output:**  
```text
Python Programming Language
```

---

## **4. `swapcase()`**  
စာလုံးကြီးကို **သေးလုံး**, သေးလုံးကို **စာလုံးကြီး** ပြောင်းမယ်။  

```python
text = "PyThOn"
print(text.swapcase())  
```
**Output:**  
```text
pYtHoN
```

---

## **5. `strip()`, `lstrip()`, `rstrip()`**  
- `strip()` → **ဘယ်ဘက်-ညာဘက် Space, Tab, Newline တွေဖယ်မယ်**  
- `lstrip()` → **ဘယ်ဘက် Space, Tab, Newline တွေဖယ်မယ်**  
- `rstrip()` → **ညာဘက် Space, Tab, Newline တွေဖယ်မယ်**  

```python
text = "   Hello World   "
print(text.strip())  
print(text.lstrip())  
print(text.rstrip())  
```
**Output:**  
```text
Hello World
Hello World   
   Hello World
```

---

## **6. `replace(old, new)`**  
String ထဲက စကားလုံး (သို့) စာလုံးတစ်ခုကို အခြားတစ်ခုနဲ့ပြောင်းမယ်။  

```python
text = "I love Java"
print(text.replace("Java", "Python"))  
```
**Output:**  
```text
I love Python
```

---

## **7. `split(separator)`**  
String ကို List အနေနဲ့ **ပိုင်းထုတ်** ပေးမယ်။  

```python
text = "apple,banana,orange"
print(text.split(","))  
```
**Output:**  
```python
['apple', 'banana', 'orange']
```

---

## **8. `join(iterable)`**  
List အနေနဲ့ရှိတဲ့ string တွေကို **string တစ်ခုအနေနဲ့ချိတ်ဆက်မယ်**။  

```python
words = ["Python", "is", "awesome"]
print(" ".join(words))  
```
**Output:**  
```text
Python is awesome
```

---

## **9. `startswith(substring)`, `endswith(substring)`**  
- `startswith()` → **String က ဒီစာလုံးနဲ့စတယ်လား?**  
- `endswith()` → **String က ဒီစာလုံးနဲ့ဆုံးတယ်လား?**  

```python
text = "Hello Python"
print(text.startswith("Hello"))  
print(text.endswith("Python"))  
```
**Output:**  
```python
True
True
```

---

## **10. `find(substring)` & `index(substring)`**  
- `find()` → **String ထဲမှာ substring ရဲ့ Index ကိုပြမယ်။ မရှိရင် -1 ပြမယ်။**  
- `index()` → **String ထဲမှာ substring ရဲ့ Index ကိုပြမယ်။ မရှိရင် Error ပေးမယ်။**  

```python
text = "Hello Python"
print(text.find("Python"))  
print(text.index("Python"))  
```
**Output:**  
```python
6
6
```

---

## **11. `count(substring)`**  
String ထဲမှာ substring **ဘယ်နှစ်ခါရှိတယ်**ဆိုတာတွက်မယ်။  

```python
text = "banana banana banana"
print(text.count("banana"))  
```
**Output:**  
```python
3
```

---

## **12. `isdigit()`, `isalpha()`, `isalnum()`**  
- `isdigit()` → **Digit (0-9) တွေပဲပါသလား?**  
- `isalpha()` → **Alphabet (A-Z, a-z) တွေပဲပါသလား?**  
- `isalnum()` → **Alphabet + Digit တွေပါလား?**  

```python
text1 = "12345"
text2 = "Python"
text3 = "Python123"

print(text1.isdigit())  # True
print(text2.isalpha())  # True
print(text3.isalnum())  # True
```

---

## **13. `zfill(width)`**  
String ရဲ့အရှေ့မှာ `0` **ဖြည့်မယ်** (length ကို fit ဖြစ်အောင်)  

```python
text = "42"
print(text.zfill(5))  
```
**Output:**  
```python
00042
```

---

## **14. `center(width, fillchar)`, `ljust(width, fillchar)`, `rjust(width, fillchar)`**  
- `center(width, fillchar)` → **String ကို ဗဟိုချထားပြီး fillchar ဖြည့်မယ်**  
- `ljust(width, fillchar)` → **ဘယ်ဘက်တွင် စတင်ပြီး fillchar ဖြည့်မယ်**  
- `rjust(width, fillchar)` → **ညာဘက်တွင် စတင်ပြီး fillchar ဖြည့်မယ်**  

```python
text = "Hello"
print(text.center(10, "-"))  
print(text.ljust(10, "-"))  
print(text.rjust(10, "-"))  
```
**Output:**  
```python
--Hello---
Hello-----
-----Hello
```

---


###  **Python String Methods (30)**

| #  | Method | Description | Example | Output |
|----|--------|-------------|---------|--------|
| 1  | `capitalize()` | ပထမစာလုံးကို Capitalized လုပ်မယ် | `"hello".capitalize()` | `"Hello"` |
| 2  | `upper()` | String ကို အကုန် Capitalized လုပ်မယ် | `"python".upper()` | `"PYTHON"` |
| 3  | `lower()` | String ကို အကုန် Small Letter ပြောင်းမယ် | `"PYTHON".lower()` | `"python"` |
| 4  | `title()` | စကားလုံးတိုင်း၏ ပထမစာလုံး Capitalized | `"hello world".title()` | `"Hello World"` |
| 5  | `swapcase()` | Capitalized & Small Letter ကို လှဲပြောင်းမယ် | `"PyThOn".swapcase()` | `"pYtHoN"` |
| 6  | `strip()` | Space, Tab, Newline တွေဖယ်မယ် | `"  text  ".strip()` | `"text"` |
| 7  | `lstrip()` | ဘယ်ဘက် Space တွေဖယ်မယ် | `"  text".lstrip()` | `"text"` |
| 8  | `rstrip()` | ညာဘက် Space တွေဖယ်မယ် | `"text  ".rstrip()` | `"text"` |
| 9  | `replace(old, new)` | စကားလုံးတစ်ခုကို အခြားတစ်ခုနဲ့ပြောင်းမယ် | `"I love Java".replace("Java", "Python")` | `"I love Python"` |
| 10 | `split(separator)` | String ကို List အနေနဲ့ ဖြတ်မယ် | `"a,b,c".split(",")` | `["a", "b", "c"]` |
| 11 | `join(iterable)` | List ထဲက Item တွေကို String ပြောင်းချိတ်မယ် | `",".join(["a", "b", "c"])` | `"a,b,c"` |
| 12 | `startswith(substring)` | ဒီစာလုံးနဲ့စတာလား? | `"hello".startswith("h")` | `True` |
| 13 | `endswith(substring)` | ဒီစာလုံးနဲ့ဆုံးတာလား? | `"hello".endswith("o")` | `True` |
| 14 | `find(substring)` | Substring ရဲ့ Index ကိုရှာမယ် | `"hello".find("l")` | `2` |
| 15 | `index(substring)` | Substring ရဲ့ Index ကိုရှာမယ် (မရှိရင် Error) | `"hello".index("o")` | `4` |
| 16 | `count(substring)` | Substring ဘယ်နှစ်ခါပါသလဲ? | `"banana".count("a")` | `3` |
| 17 | `isdigit()` | Digit (0-9) တွေပဲပါလား? | `"123".isdigit()` | `True` |
| 18 | `isalpha()` | Alphabet (A-Z, a-z) တွေပဲပါလား? | `"abc".isalpha()` | `True` |
| 19 | `isalnum()` | Alphabet + Digit တွေပဲပါလား? | `"abc123".isalnum()` | `True` |
| 20 | `isspace()` | Space တွေပဲလား? | `"   ".isspace()` | `True` |
| 21 | `isupper()` | Capitalized ဖြစ်လား? | `"HELLO".isupper()` | `True` |
| 22 | `islower()` | Small Letter ဖြစ်လား? | `"hello".islower()` | `True` |
| 23 | `istitle()` | Title Case ဖြစ်လား? | `"Hello World".istitle()` | `True` |
| 24 | `zfill(width)` | Length fit အောင် `0` ဖြည့်မယ် | `"42".zfill(5)` | `"00042"` |
| 25 | `center(width, fillchar)` | String ကို ဗဟိုချထားပြီး fillchar ဖြည့်မယ် | `"hi".center(6, "-")` | `"--hi--"` |
| 26 | `ljust(width, fillchar)` | ဘယ်ဘက်ခြမ်းမှာ Fillchar ဖြည့်မယ် | `"hi".ljust(6, "-")` | `"hi----"` |
| 27 | `rjust(width, fillchar)` | ညာဘက်ခြမ်းမှာ Fillchar ဖြည့်မယ် | `"hi".rjust(6, "-")` | `"----hi"` |
| 28 | `partition(substring)` | String ကို Substring နဲ့ပိုင်းမယ် | `"hello world".partition(" ")` | `('hello', ' ', 'world')` |
| 29 | `rpartition(substring)` | နောက်ဆုံးဆုံးသော substring နဲ့ ပိုင်းမယ် | `"hello world".rpartition(" ")` | `('hello', ' ', 'world')` |
| 30 | `format()` | String ကို Dynamic Data ဖြည့်မယ် | `"My name is {}".format("Kyaw")` | `"My name is Kyaw"` |

---

