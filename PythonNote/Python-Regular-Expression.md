
Python မှာ Regular Expressions (RegEx) ကို `re` module နဲ့ အသုံးပြုနိုင်ပါတယ်။ RegEx ကို string များထဲမှာ pattern matching, searching, replacing, splitting စတာတွေ အတွက် အသုံးပြုနိုင်ပါတယ်။

---

## **1. Regular Expressions Functions in Python (`re` module)**

| Function | Description | Example |
|----------|------------|---------|
| `re.match(pattern, string)` | String ရဲ့အစမှာ pattern နဲ့ တူသလား စစ် | `re.match(r'Hello', 'Hello World')` |
| `re.search(pattern, string)` | String တစ်ခုလုံးထဲမှာ pattern ကို ရှာ | `re.search(r'World', 'Hello World')` |
| `re.findall(pattern, string)` | String ထဲမှာ pattern ကို find လုပ်ပြီး list အနေနဲ့ပြန် | `re.findall(r'\d+', 'My number is 12345')` |
| `re.finditer(pattern, string)` | Matches တွေအားလုံးကို iterator အနေနဲ့ ပြန် | `re.finditer(r'\d+', 'My number is 12345')` |
| `re.sub(pattern, replace, string)` | String ထဲက pattern တွေကို replace | `re.sub(r'Python', 'JavaScript', 'I love Python!')` |
| `re.split(pattern, string)` | Pattern ကို 기준ထားပြီး string ကို ခွဲ | `re.split(r'\s+', 'Hello World! Python is fun')` |

---

## **2. Common Regular Expressions Patterns**

| Pattern | Description | Example |
|---------|-------------|---------|
| `.` | Any character except newline | `r'c.t'` → `cat`, `cut`, `cot` |
| `^` | String ရဲ့အစကို match | `r'^Hello'` → `'Hello World'` (✅) |
| `$` | String ရဲ့အဆုံးကို match | `r'World$'` → `'Hello World'` (✅) |
| `\d` | Digits (0-9) | `r'\d+'` → `'123'` (✅) |
| `\D` | Non-digits | `r'\D+'` → `'Hello'` (✅) |
| `\w` | Alphanumeric characters | `r'\w+'` → `'Hello123'` (✅) |
| `\W` | Non-alphanumeric characters | `r'\W+'` → `'@#!'` (✅) |
| `\s` | Whitespace (space, tab, newline) | `r'\s+'` → `'   '` (✅) |
| `\S` | Non-whitespace characters | `r'\S+'` → `'Hello'` (✅) |
| `*` | 0 or more times | `r'ca*t'` → `ct`, `cat`, `caaat` |
| `+` | 1 or more times | `r'ca+t'` → `cat`, `caaat` (❌`ct`) |
| `?` | 0 or 1 time (optional) | `r'ca?t'` → `ct`, `cat` (❌`caaat`) |
| `{n}` | Exactly n times | `r'\d{3}'` → `'123'` (✅) |
| `{n,}` | At least n times | `r'\d{2,}'` → `'123'` (✅) |
| `{n,m}` | Between n and m times | `r'\d{2,4}'` → `'123'` (✅) `'12345'` (❌) |
| `[]` | Character set | `r'[aeiou]'` → `'a'`, `'e'`, `'i'` |
| `[^]` | Negate character set | `r'[^aeiou]'` → `'b'`, `'c'`, `'d'` |
| `|` | OR operator | `r'cat|dog'` → `'cat'`, `'dog'` |
| `()` | Grouping | `r'(Hello|Hi) World'` → `'Hello World'`, `'Hi World'` |

---

## **3. Examples of Regular Expressions in Python**

### **(1) Check if a string starts with "Hello"**
```python
import re
text = "Hello, how are you?"
match = re.match(r'^Hello', text)
print(bool(match))  # Output: True
```

### **(2) Find all numbers in a string**
```python
import re
text = "I have 2 apples, 3 oranges, and 10 bananas."
numbers = re.findall(r'\d+', text)
print(numbers)  # Output: ['2', '3', '10']
```

### **(3) Replace all digits with `#`**
```python
import re
text = "My phone number is 123-456-7890."
masked_text = re.sub(r'\d', '#', text)
print(masked_text)  # Output: My phone number is ###-###-####
```

### **(4) Extract email addresses from a string**
```python
import re
text = "Contact me at test@example.com and admin@site.org"
emails = re.findall(r'[\w\.-]+@[\w\.-]+\.\w+', text)
print(emails)  # Output: ['test@example.com', 'admin@site.org']
```

### **(5) Split a sentence into words**
```python
import re
text = "Hello, welcome to the world of Python!"
words = re.split(r'\s+', text)
print(words)  # Output: ['Hello,', 'welcome', 'to', 'the', 'world', 'of', 'Python!']
```

---

**🔹 Summary**
- `re.match()` → String ရဲ့အစမှာ pattern တူလား စစ်
- `re.search()` → String ထဲမှာ pattern တစ်ခုရှိလား ရှာ
- `re.findall()` → Pattern ကို find လုပ်ပြီး list အနေနဲ့ပြန်
- `re.sub()` → String ထဲက pattern တွေကို တခြား string နဲ့အစားထိုး
- `re.split()` → Pattern ကို 기준ထားပြီး string ကို ခွဲ

**🔹 Useful Patterns**
- `\d+` → Numbers only
- `\w+` → Words only
- `\s+` → Whitespaces only
- `.*` → Any character (zero or more)
- `^text` → Text starts with
- `text$` → Text ends with
- `[a-z]` → Lowercase letters
- `[A-Z]` → Uppercase letters
- `\bword\b` → Whole word matching

---
## DeepSeek 

---

### **Regular Expressions အခြေခံ (Python `re` Module)**
Python တွင် `re` module ကို အသုံးပြု၍ Regex များကို လုပ်ဆောင်နိုင်ပါသည်။  
အဓိက Function များ: `re.search()`, `re.match()`, `re.findall()`, `re.sub()`, `re.split()`.

---

### **Regex Metacharacters ဇယား**
| **Metacharacter** | **အမည်**                 | **ဖော်ပြချက်**                                                                 | **ဥပမာ**                     |
|--------------------|--------------------------|------------------------------------------------------------------------------|-----------------------------|
| `.`                | Dot                      | မည်သည့် Character ကိုမဆို ကိုက်ညီသည် (Newline မှလွဲ၍)                        | `a.c` → "abc", "a@c"        |
| `^`                | Caret                    | စာကြောင်းအစ (Start of String)                                             | `^Hello` → "Hello World"    |
| `$`                | Dollar                   | စာကြောင်းအဆုံး (End of String)                                            | `World$` → "Hello World"    |
| `*`                | Asterisk                 | ယခင် Character ကို **၀ သို့မဟုတ် အကြိမ်များစွာ** ကိုက်ညီသည်                     | `a*` → "", "a", "aa"        |
| `+`                | Plus                     | ယခင် Character ကို **၁ ကြိမ် သို့မဟုတ် အကြိမ်များစွာ** ကိုက်ညီသည်               | `a+` → "a", "aa"            |
| `?`                | Question Mark            | ယခင် Character ကို **၀ သို့မဟုတ် ၁ ကြိမ်** ကိုက်ညီသည်                          | `a?` → "", "a"              |
| `{m,n}`            | Curly Braces             | ယခင် Character ကို **m ကြိမ်မှ n ကြိမ်အထိ** ကိုက်ညီသည်                          | `a{2,3}` → "aa", "aaa"      |
| `[ ]`              | Character Class          | အတွင်းရှိ Character တစ်ခုခုနှင့် ကိုက်ညီသည်                                      | `[aeiou]` → "a", "e"        |
| `|`                | Pipe (OR)                | ဘယ်ဘက် သို့မဟုတ် ညာဘက်ရှိ Pattern နှင့် ကိုက်ညီသည်                              | `cat|dog` → "cat", "dog"    |
| `( )`              | Group                    | Pattern ကို Group အဖြစ် သတ်မှတ်သည်၊ Capturing လုပ်သည်                          | `(ab)+` → "abab"            |
| `\d`               | Digit                    | ဂဏန်း (0-9) နှင့် ကိုက်ညီသည် (`[0-9]` နှင့်တူညီသည်)                              | `\d+` → "123"               |
| `\w`               | Word Character           | စာလုံး၊ ဂဏန်း၊ နှင့် Underscore (`[a-zA-Z0-9_]` နှင့်တူညီသည်)                   | `\w+` → "user123"           |
| `\s`               | Whitespace               | နေရာလွတ် (Space, Tab, Newline)                                              | `\s+` → "   "               |
| `\b`               | Word Boundary            | စာလုံးတစ်လုံး၏ အစ သို့မဟုတ် အဆုံး (ဥပမာ: `\bword\b`)                           | `\bcat\b` → "cat" in "a cat"|

---

### **Regex Flags (Modifiers)**
Python တွင် Flags များကို Pattern ၏ လုပ်ဆောင်ချက်ကို ပြောင်းလဲရန် အသုံးပြုသည်။

| **Flag**         | **အမည်**           | **ဖော်ပြချက်**                                                                 |
|------------------|--------------------|------------------------------------------------------------------------------|
| `re.IGNORECASE`  | Case Insensitive   | အကြီးအသေး မခွဲခြားဘဲ ကိုက်ညီသည် (ဥပမာ: `re.compile(r"hello", re.I)`)          |
| `re.MULTILINE`   | Multiline Mode     | `^` နှင့် `$` ကို စာကြောင်းတိုင်း၏ အစ/အဆုံးနှင့် ကိုက်ညီသည်                      |
| `re.DOTALL`      | Dot Matches All    | `.` သည် Newline အပါအဝင် မည်သည့် Character နှင့်မဆို ကိုက်ညီသည်                   |
| `re.ASCII`       | ASCII-Only         | `\w`, `\d`, စသည် တို့ကို ASCII Characters များနှင့်သာ ကိုက်ညီသည်                 |

---

### **ဥပမာများ (Python Code ဖြင့်)**

#### 1. **ရိုးရှင်းသော Search**
```python
import re

text = "Python is fun!"
pattern = r"fun"
result = re.search(pattern, text)
print(result.group())  # Output: fun
```

#### 2. **ဖုန်းနံပါတ် ရှာဖွေခြင်း (ဥပမာ: 09-12345678)**
```python
text = "Contact: 09-12345678, 09-87654321"
pattern = r"\d{2}-\d{8}"
matches = re.findall(pattern, text)
print(matches)  # Output: ['09-12345678', '09-87654321']
```

#### 3. **Email Validation**
```python
email = "user@example.com"
pattern = r"^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$"
if re.match(pattern, email):
    print("Valid Email!")
```

#### 4. **စာသားအစားထိုးခြင်း (re.sub)**
```python
text = "Python is hard. Python is great."
new_text = re.sub(r"hard", "easy", text)
print(new_text)  # Output: "Python is easy. Python is great."
```

#### 5. **စာလုံးများခွဲခြားခြင်း (re.split)**
```python
text = "Apple,Banana;Cherry"
result = re.split(r"[,;]", text)
print(result)  # Output: ['Apple', 'Banana', 'Cherry']
```

---

### **အဆင့်မြင့် Regex နမူနာများ**
- **Lookahead & Lookbehind**  
  ```python
  # Positive Lookahead: "cat" ပြီးနောက် "123" ရှိသော String
  re.findall(r"cat(?=123)", "cat123")  # Output: ['cat']
  ```

- **Non-Greedy Quantifier (?)**:  
  ```python
  # Greedy: <.*> → "<html><head>"
  # Non-Greedy: <.*?> → "<html>", "<head>"
  re.findall(r"<.*?>", "<html><head>")
  ```

---

### **မှတ်ချက်**
- **Raw String (`r""`)**: Python တွင် Backslashes (`\`) များကို မထိခိုက်စေရန် `r""` ဖြင့် စတင်ရေးပါ။
- **Special Characters** များကို Escape လုပ်ရန် `\` သုံးပါ။ ဥပမာ: `\.`, `\*`။
- Regex သည် စွယ်စုံသုံးနိုင်သော်လည်း ရှုပ်ထွေးနိုင်သဖြင့် [regex101.com](https://regex101.com/) ကဲ့သို့သော Tool များဖြင့် စမ်းသပ်ပါ။
---

