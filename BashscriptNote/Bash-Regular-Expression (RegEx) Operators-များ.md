

### **Regular Expression (RegEx) Operators - အခြေခံများ**  

Regular Expression (RegEx) ဆိုတာ **Text Processing** လုပ်တဲ့အခါ **Pattern Matching** အတွက်အသုံးများတဲ့ Syntax တစ်ခုပဲဖြစ်ပါတယ်။  
Linux, Bash, Python, JavaScript, PHP, MySQL, Vim, LazyVim, Zsh, Sed, Awk, Grep စတဲ့ **Shell Scripting** နဲ့ **Programming** တွေအများကြီးမှာအသုံးများပါတယ်။  

---

## **1️⃣ Characters & Meta-characters (သင်္ကေတများ)**  

### **(1) Literal Characters** - (ပုံမှန်စာလုံးများ)  
RegEx မှာ အက္ခရာ (A-Z, a-z), နံပါတ် (0-9), အခြား character (%, &, @, #...) တွေကို **Literal Characters** လို့ခေါ်တယ်။  
🔹 **Example**  
```plaintext
hello
123
@#$%
```
🔹 **Matching**  
- `hello` ဟာ `"hello world"` မှာကိုက်မယ်  
- `123` ဟာ `"order number 12345"` မှာကိုက်မယ်  

---

### **(2) Dot (`.`) - တစ်လုံးတည်းကို ကိုက်ညီစေမယ့် Operator**  
- `.` (dot) က **Single Character** **(အချည်းနှီး မဖြစ်ရ)** ကို **Wildcard** လိုချင်းဖြေနိုင်တယ်။  
🔹 **Example**  
```plaintext
c.t
```
🔹 **Matching**  
- `"cat"` ✅  
- `"cot"` ✅  
- `"cut"` ✅  
- `"ct"` ❌ (အချည်းနှီးမဖြစ်ရ)  

---

### **(3) Brackets (`[]`) - Character Set**  
- `[...]` က **ရှေးမှုများ** **(Choices)** ကိုဖော်ပြတာ။  
🔹 **Example**  
```plaintext
gr[ae]y
```
🔹 **Matching**  
- `"gray"` ✅  
- `"grey"` ✅  
- `"gry"` ❌  

---

### **(4) Dash (`-`) - Range Operator**  
- `[a-z]`, `[A-Z]`, `[0-9]` ဆိုတာ **Range** ကိုဖော်ပြတယ်။  
🔹 **Example**  
```plaintext
[0-9]
[a-z]
[A-Z]
```
🔹 **Matching**  
- `"5"` ✅ `[0-9]`  
- `"x"` ✅ `[a-z]`  
- `"Z"` ✅ `[A-Z]`  

---

### **(5) Caret (`^`) - Negative Character Set**  
- `[^...]` ဆိုရင် ထိုစာလုံးများ မပါဘဲ အခြား character ကိုချင်တယ်။  
🔹 **Example**  
```plaintext
[^aeiou]
```
🔹 **Matching**  
- `"b"` ✅ (မရှိတဲ့ a, e, i, o, u ကိုပြုမယ်)  
- `"a"` ❌  

---

### **(6) Pipe (`|`) - OR Operator**  
- `|` က **OR Condition** ကိုဖော်ပြတယ်။  
🔹 **Example**  
```plaintext
cat|dog
```
🔹 **Matching**  
- `"cat"` ✅  
- `"dog"` ✅  
- `"bat"` ❌  

---

## **2️⃣ Position Anchors (စတင်မှု / အဆုံးမှာကိုက်စေတဲ့ Operator)**  

### **(1) Caret (`^`) - Line Start (စမှာကိုက်စေမယ်)**  
- `^word` ဆိုရင် `"word"` ဟာ **စာကြောင်းအစမှာဖြစ်မှ** ကိုက်ညီမယ်။  
🔹 **Example**  
```plaintext
^hello
```
🔹 **Matching**  
- `"hello world"` ✅  
- `"world hello"` ❌  

---

### **(2) Dollar (`$`) - Line End (နောက်ဆုံးမှာကိုက်စေမယ်)**  
- `word$` ဆိုရင် `"word"` ဟာ **စာကြောင်းအဆုံးမှာဖြစ်မှ** ကိုက်ညီမယ်။  
🔹 **Example**  
```plaintext
world$
```
🔹 **Matching**  
- `"hello world"` ✅  
- `"world hello"` ❌  

---

## **3️⃣ Quantifiers (ထပ်နေမှုကို ကိုင်တွယ်မယ့် Operator များ)**  

### **(1) Asterisk (`*`) - Zero or More**  
- `A*` ဆိုရင် `A` ဟာ **မရှိလည်းရ, တစ်ခါရှိလည်းရ**  
🔹 **Example**  
```plaintext
ba*
```
🔹 **Matching**  
- `"b"` ✅  
- `"ba"` ✅  
- `"baaaaaa"` ✅  

---

### **(2) Plus (`+`) - One or More**  
- `A+` ဆိုရင် `A` ဟာ **တစ်ခါရှိမှ** ကိုက်မယ်။  
🔹 **Example**  
```plaintext
ba+
```
🔹 **Matching**  
- `"b"` ❌  
- `"ba"` ✅  
- `"baaaaaa"` ✅  

---

### **(3) Question Mark (`?`) - Zero or One**  
- `A?` ဆိုရင် `A` ဟာ **မရှိလည်းရ, တစ်ခါရှိလည်းရ**  
🔹 **Example**  
```plaintext
colou?r
```
🔹 **Matching**  
- `"color"` ✅  
- `"colour"` ✅  
- `"colouur"` ❌  

---

### **(4) Curly Braces (`{}`) - Specific Count**  
- `A{n}` 👉 **A ကို `n` ခါရှိမှ ကိုက်မယ်**  
- `A{n,}` 👉 **A ကို `n` ခါရှိမှ ကိုက်မယ်**  
- `A{n,m}` 👉 **A ကို `n` ခါ ~ `m` ခါရှိမှ ကိုက်မယ်**  
🔹 **Example**  
```plaintext
ba{2}
```
🔹 **Matching**  
- `"b"` ❌  
- `"ba"` ❌  
- `"baa"` ✅  

---

## **4️⃣ Special Escape Characters (သင်္ကေတများကို Literal သို့ပြောင်းမယ့် Operator များ)**  

### **(1) Backslash (`\`) - Escape Character**  
- `\.` 👉 **Literal Dot**  
- `\*` 👉 **Literal Asterisk**  
- `\$` 👉 **Literal Dollar**  
🔹 **Example**  
```plaintext
hello\.
```
🔹 **Matching**  
- `"hello."` ✅  
- `"hello!"` ❌  

---

### **(2) Common Escape Sequences**  
| Syntax | Meaning |
|--------|---------|
| `\d` | Digits (0-9) |
| `\D` | Non-Digits |
| `\w` | Word Characters (A-Z, a-z, 0-9, _) |
| `\W` | Non-Word Characters |
| `\s` | Whitespace (space, tab, newline) |
| `\S` | Non-Whitespace |

---

## **🔥 Summary**  
| Operator | Description                  |     |
| -------- | ---------------------------- | --- |
| `.`      | Any character except newline |     |
| `[]`     | Character set                |     |
| `[^]`    | Negated character set        |     |
| `*`      | Zero or more                 |     |
| `+`      | One or more                  |     |
| `?`      | Zero or one                  |     |
| `{n,m}`  | Between `n` and `m` times    |     |
|   \|     | OR condition                 |     |
| `^`      | Start of line                |     |
| `$`      | End of line                  |     |
| `\`      | Escape character             |     |

---
