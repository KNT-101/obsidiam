
## 🔹 `any()` နဲ့ `all()` သဘောတရား
Python မှာ `any()` နဲ့ `all()` တို့ကို **iterable (list, tuple, set, dictionary keys, etc.)** များအတွက် logic operation တွေလုပ်ဆောင်ရန် အသုံးပြုကြတယ်။  

### ✅ `any(iterable)`
👉 `any()` သည် **iterable မှာ element တစ်ခုခု true ဖြစ်နေရုံဖြင့်** `True` ပြန်ပေးမည်။   
👉 **အားလုံး `False` ဖြစ်ရင်သာ** `False` ပြန်မယ်။  
 
#### ✨ Example 1: `any()` Basic Usage
```python
values = [0, 0, 1, 0]
print(any(values))  # True (တစ်ခုခု `True` ဖြစ်နေသည်)

values = [0, 0, 0, 0]
print(any(values))  # False (အားလုံး `False` ဖြစ်နေသည်)
```

---

### ✅ `all(iterable)`
👉 `all()` သည် **iterable ထဲရှိ element အားလုံး true ဖြစ်မှသာ** `True` ပြန်ပေးမည်။  
👉 **တစ်ခုခု false ဖြစ်နေပါက** `False` ပြန်မည်။  

#### ✨ Example 2: `all()` Basic Usage
```python
values = [1, 2, 3, 4]
print(all(values))  # True (အားလုံး `True` ဖြစ်သည်)

values = [1, 0, 3, 4]
print(all(values))  # False (တစ်ခုခု `False` ဖြစ်နေသည်)
```

---

### 🔹 `any()` & `all()` ကို Dictionary နဲ့ အသုံးပြုပုံ  

Dictionary မှာ key-value pairs တွေနဲ့ `any()` နဲ့ `all()` ကို အသုံးပြုနိုင်တယ်။  

#### Example 3: Dictionary Key Checking

```python
users = {'name': 'Kyaw', 'email': 'kyaw@example.com', 'age': 25}
required_fields = ['name', 'email']

# Check if at least one required field is missing
print(any(field not in users for field in required_fields))  # False (အားလုံးရှိနေတယ်)

# Check if all required fields exist
print(all(field in users for field in required_fields))  # True (အားလုံးရှိနေတယ်)
```

---

### 🔹 `any()` & `all()` ကို Condition Checking တွေမှာ အသုံးပြုနိုင်  
####  Example 4: `any()` ကို Password Strength Check တွင် သုံးခြင်း

```python
password = "Hello123"

checks = [
    any(char.isdigit() for char in password),  # အနည်းဆုံး တစ်လုံး အရေအတွက်ပါလား?
    any(char.isupper() for char in password),  # အနည်းဆုံး တစ်လုံး အကြီးစာလုံးပါလား?
    any(char.islower() for char in password)   # အနည်းဆုံး တစ်လုံး အသေးစာလုံးပါလား?
]

if all(checks):  
    print("Password is strong! 💪")
else:
    print("Password is weak! ⚠️")
```

---

### Example 5: `any()` & `all()` ကို Form Validation တွင် အသုံးပြုခြင်း

```python
user_input = {'username': 'kyaw', 'email': 'kyaw@example.com', 'password': 'test123'}

required_fields = ['username', 'email', 'password']

# Required fields all exist?
if all(field in user_input and user_input[field] for field in required_fields):
    print("Form is valid ✅")
else:
    print("Form is invalid ❌")
```

---

### 🔹 `any()` & `all()` ကို **Short-circuit** Checking လုပ်နိုင်ခြင်း  
`any()` **မှာ** ပထမဆုံး `True` တစ်ခုတွေ့လျှင် **နောက်ထပ် elements မစစ်တော့ဘဲ** `True` ပြန်ပေးတယ်။  
`all()` **မှာ** ပထမဆုံး `False` တစ်ခုတွေ့လျှင် **နောက်ထပ် elements မစစ်တော့ဘဲ** `False` ပြန်ပေးတယ်။  

#### ✨ Example 6: Short-circuit Behavior  
```python
def check(x):
    print(f"Checking {x}")
    return x > 0

print(any(check(n) for n in [-1, 0, 3, 5]))  
# Checking -1
# Checking 0
# Checking 3 (True ဖြစ်သွားလို့ နောက်ထပ်မစစ်တော့)
# True
```

---

###  အကျဉ်းချုပ်

- ✅ `any()` 👉 **တစ်ခုခု `True` ဖြစ်ရုံနဲ့** `True` ပြန်မယ်။
- ✅ `all()` 👉 **အားလုံး `True` ဖြစ်မှသာ** `True` ပြန်မယ်။
- ✅ Short-circuit behavior **(နောက်ထပ်မစစ်ရဘဲ အမြန်ဆုံးဆုံးဖြတ်နိုင်)**  
- ✅ **Form validation, password checking, dictionary key checking** တွေမှာ အသုံးဝင်  

---