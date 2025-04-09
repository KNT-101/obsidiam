
Python `collections` module ထဲမှာပါတဲ့ `ChainMap`, `Counter`, `defaultdict`, `deque`, `namedtuple` တို့ကို အကုန်လုံးကို example တွေနဲ့အတူ ရှင်းပြမယ်နော်။ 😊  

---

## 1️⃣ `ChainMap`
`ChainMap` ကို dictionary တို့ကို chaining (ချိတ်ဆွဲ)လုပ်ဖို့သုံးတယ်။ Dictionary များစွာကို တစ်ခုတည်းသော view မှာ တွေ့နိုင်သလို, value တွေကို ပြောင်းလဲနိုင်တယ်။  

### Example:
```python
from collections import ChainMap

dict1 = {'a': 1, 'b': 2}
dict2 = {'b': 3, 'c': 4}

# ChainMap ဖြင့် dictionary နှစ်ခုကို ချိတ်ဆွဲ
chain = ChainMap(dict1, dict2)

print(chain['a'])  # 1 (dict1 ထဲမှာရှိတယ်)
print(chain['b'])  # 2 (dict1 ထဲမှာရှိတဲ့ value ကိုပဲ ယူမယ်)
print(chain['c'])  # 4 (dict2 ထဲမှာရှိတဲ့ value ကိုယူမယ်)

# Update value (dict1 ထဲမှာရှိတဲ့ value ပဲ update ဖြစ်မယ်)
chain['b'] = 10
print(dict1)  # {'a': 1, 'b': 10}
```

---

## 2️⃣ `Counter`
`Counter` ကို iterable (list, string, tuple) ထဲက element တွေကို count လုပ်ဖို့ သုံးတယ်။  

### Example:
```python
from collections import Counter

data = ['apple', 'banana', 'apple', 'orange', 'banana', 'banana']

counter = Counter(data)

print(counter)  # {'banana': 3, 'apple': 2, 'orange': 1}

# Count value အများဆုံး 2 ခုကို ယူချင်ရင်
print(counter.most_common(2))  # [('banana', 3), ('apple', 2)]
```

---

## 3️⃣ `defaultdict`
`defaultdict` ကို normal dictionary ထက်ပိုပြီး အဆင်ပြေတဲ့နေရာကတော့, key မရှိတဲ့ value ကို default value နဲ့ initialize လုပ်ပေးနိုင်တာပါ။  

### Example:
```python
from collections import defaultdict

# Default value အနေနဲ့ list() ထည့်မယ်
d = defaultdict(list)

d['a'].append(1)
d['a'].append(2)
d['b'].append(3)

print(d)  # {'a': [1, 2], 'b': [3]}
print(d['c'])  # []  (default value list() ဖြစ်လို့ empty list return မယ်)
```

---

## 4️⃣ `deque`
`deque` (double-ended queue) ဟာ list ထက် `append` နဲ့ `pop` ကို ပိုမြန်မြန်လုပ်နိုင်တယ်။  

### Example:
```python
from collections import deque

dq = deque([1, 2, 3])
dq.append(4)   # နောက်ဆုံးမှာထည့်မယ်
dq.appendleft(0)  # စာရွက်အစမှာထည့်မယ်

print(dq)  # deque([0, 1, 2, 3, 4])

dq.pop()  # နောက်ဆုံးကနေတစ်ခုဖယ်မယ်
dq.popleft()  # ပထမဆုံးကနေတစ်ခုဖယ်မယ်

print(dq)  # deque([1, 2, 3])
```

---

## 5️⃣ `namedtuple`
`namedtuple` ကို class တစ်ခုလိုပဲ သုံးနိုင်ပြီး, data ကို named fields နဲ့ သိမ်းနိုင်တယ်။  

### Example:
```python
from collections import namedtuple

Person = namedtuple('Person', ['name', 'age'])
p = Person(name="Kyaw", age=25)

print(p.name)  # Kyaw
print(p.age)  # 25
```

---

👉 **ဒီ module တွေက data structure ကို ပိုမိုအဆင်ပြေစေတဲ့ built-in tools တွေပါ။ ဘယ်လိုသုံးရမလဲဆိုတာ တစ်ခုချင်းစီနဲ့ သက်ဆိုင်တဲ့ အကြောင်းအရာနဲ့ ပြလိုက်ပြီနော်။ 😍**


---

`collections` module ထဲမှာ `ChainMap`, `Counter`, `defaultdict`, `deque`, `namedtuple` တို့အပြင် နောက်ထပ် အသုံးဝင်တဲ့ data structures တွေလည်း ပါသေးတယ်။ 

---

##  `OrderedDict`
`OrderedDict` က **Python 3.7 နောက်ပိုင်းမှာ normal `dict` တွေကလည်း order ထားပေးနိုင်ပြီးသားဖြစ်ပေမယ့်**, `OrderedDict` ကို သုံးပြီး extra functionality တွေထပ်ထည့်နိုင်တယ်။  

### Example:
```python
from collections import OrderedDict

# Dictionary ကို order တူအောင်သိမ်းမယ်
ordered_dict = OrderedDict()
ordered_dict['apple'] = 3
ordered_dict['banana'] = 2
ordered_dict['orange'] = 5

print(ordered_dict)  # OrderedDict([('apple', 3), ('banana', 2), ('orange', 5)])

# Last item ကိုဖျက်ပြီး ပထမဆုံးမှာ ထပ်ထည့်မယ်
ordered_dict.move_to_end('banana', last=False)
print(ordered_dict)  # OrderedDict([('banana', 2), ('apple', 3), ('orange', 5)])
```

---

##  `UserDict`
`UserDict` ကို normal dictionary တစ်ခုလိုသုံးနိုင်ပြီး, `dict` ကို subclassing လုပ်လိုက်တဲ့အခါ, `dict` ကို directly subclass မလုပ်ပဲ `UserDict` ကို subclass လုပ်တာ ပိုမို flexible ဖြစ်စေတယ်။  

### Example:
```python
from collections import UserDict

class MyDict(UserDict):
    def __setitem__(self, key, value):
        if isinstance(value, int) and value >= 0:
            super().__setitem__(key, value)
        else:
            raise ValueError("Only non-negative integers are allowed!")

data = MyDict()
data['a'] = 10
print(data)  # {'a': 10}

# data['b'] = -5  # Error: ValueError: Only non-negative integers are allowed!
```

---

##  `UserList`
`UserList` ကို list ကို subclassing လုပ်ချင်တဲ့အခါ အသုံးပြုနိုင်တယ်။  

### Example:
```python
from collections import UserList

class MyList(UserList):
    def append(self, item):
        if isinstance(item, int):
            super().append(item)
        else:
            raise TypeError("Only integers are allowed!")

lst = MyList([1, 2, 3])
lst.append(4)
print(lst)  # [1, 2, 3, 4]

# lst.append('a')  # Error: TypeError: Only integers are allowed!
```

---

##  `UserString`
`UserString` ကို string ကို subclassing လုပ်ချင်တဲ့အခါ သုံးနိုင်တယ်။  

### Example:
```python
from collections import UserString

class MyString(UserString):
    def upper(self):
        return self.data.upper()

s = MyString("hello")
print(s.upper())  # "HELLO"
```

---

 **Summary**
 
| Collection Type | Description |
|---------------|------------|
| `ChainMap` | Multiple dictionaries ကို single view တစ်ခုအနေနဲ့ ကိုင်တွယ်နိုင် |
| `Counter` | Iterable မှာပါတဲ့ element တွေကို count လုပ်နိုင် |
| `defaultdict` | Key မရှိတဲ့အခါ default value ကို auto-generate |
| `deque` | List ထက် append/popleft operations မြန်တဲ့ double-ended queue |
| `namedtuple` | Named fields ပါတဲ့ tuple |
| `OrderedDict` | Ordered dictionary |
| `UserDict` | Custom dictionary subclass |
| `UserList` | Custom list subclass |
| `UserString` | Custom string subclass |

**`collections` module ထဲမှာပါတဲ့ data structures တွေကို သုံးပြီး Python မှာ data ကို ပိုမို အဆင်ပြေစွာ ကိုင်တွယ်နိုင်ပါတယ်။**

---

`collections` ထဲမှာပါတဲ့ `defaultdict`, `deque`, `Counter`, `OrderedDict`, `ChainMap`, `namedtuple`, `UserDict`, `UserList`, `UserString` တို့ကို **methods (မက်ထက်) မဟုတ်ဘဲ, classes (ခလပ်စစ်) တွေလို့ ခေါ်လို့ရပါတယ်**။  

🔹 **Method မဟုတ်ဘူး → `defaultdict()`, `Counter()`, `deque()` တွေက class တွေပဲ**  
🔹 **Class များဖြစ်တဲ့အတွက် object တစ်ခုတည်ဆောက်ရင်တော့ method တွေပါလာမယ်**  

---

### Example: `defaultdict` (Class)

```python
from collections import defaultdict

# defaultdict object တစ်ခု create လုပ်မယ်
d = defaultdict(int)  # Default value ကို `int()` ပြုလုပ်မယ်

# Methods တွေကို သုံးနိုင်
d['a'] += 1  # defaultdict မှာ key မရှိဘူးဆိုရင်, default value 0 ဖြစ်မယ်
print(d)  # defaultdict(<class 'int'>, {'a': 1})

# Method တွေကို စစ်ကြည့်မယ်
print(dir(d))  # ['clear', 'copy', 'default_factory', 'fromkeys', 'get', ...]
```
👉 **`defaultdict` ဟာ class ဖြစ်တယ်။ object တည်ဆောက်တဲ့အခါ default value ကိုသတ်မှတ်နိုင်တယ်။**  

---

### Example: `deque` (Class with Methods)

```python
from collections import deque

dq = deque([1, 2, 3])

# `append()` method
dq.append(4)

# `popleft()` method
dq.popleft()

print(dq)  # deque([2, 3, 4])
```
👉 **`deque` ဟာ class ဖြစ်ပြီး, `append()`, `popleft()` တို့လို method တွေပါဝင်တယ်။**  

---

### Example: `Counter` (Class with Methods)

```python
from collections import Counter

data = ['a', 'b', 'a', 'c', 'b', 'b']
counter = Counter(data)

# `most_common()` method
print(counter.most_common(2))  # [('b', 3), ('a', 2)]
```
👉 **`Counter` ဟာ class ဖြစ်ပြီး, `most_common()` တို့လို method တွေ ပါဝင်တယ်။**  

---

#### **သိထားရမယ့် အချက်**

✅ `collections` ထဲက `defaultdict`, `Counter`, `deque`, `OrderedDict` စတဲ့ **class တွေ** ကို method တွေလို့ မခေါ်သင့်ပါဘူး။  
✅ **Methods** တွေက class တွေအတွင်းမှာပါတဲ့ function တွေပဲဖြစ်တယ်။ (ဥပမာ - `append()`, `most_common()` )  
✅ `dir(object)` ကိုသုံးပြီး method တွေကို စစ်နိုင်တယ်။  

**Shortcut ကိုယ်တိုင်တည်ဆောက်နိုင်တဲ့ classes တွေမို့ collections module ထဲက tool တွေကို အသုံးပြုလို့ ပိုမို လွယ်ကူစေတယ်။**

---