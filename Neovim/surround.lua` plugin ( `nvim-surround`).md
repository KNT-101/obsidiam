
`surround.lua` plugin (သို့မဟုတ် `nvim-surround`) မှာ **စာလုံးတစ်ပတ်လုံးကို surround, delete, change** လုပ်နိုင်တဲ့ commands တွေကို အသုံးပြုပါတယ်။ အခုမင်းမေးတဲ့ `ysiw`, `yst"`, `ds"`, `cs"` ရဲ့ အလုပ်လုပ်ပုံတွေကို အခုရှင်းပြပေးမယ်။ 😊

---

### **Command တွေရဲ့ အဓိပ္ပါယ်**
#### **1. `ys` (You Surround)**
- **`ys` + motion + delimiter**  
  - **စာသားတစ်ခုကို surround လုပ်တယ်။**
    - **`ysiW"`**  
      - Cursor ရဲ့နေရာမှာ Surround motion (Inner Word - iW) ကို Double Quotes `"` နဲ့ Surround လုပ်မယ်။
    - **`ysiW{`**  
      - Inner Word ကို `{}` နဲ့ surround လုပ်မယ်။

- **Motion** တွေ:
  - **iw** = inner word (လက်ရှိ word)
  - **iW** = inner WORD (အကျယ်ကျယ် word)
  - **ap** = a paragraph (လက်ရှိ paragraph)

#### **2. `yst`**
- **`yst"`** ဆိုတာ `ys` command နဲ့ motion `t"` (up to the next `"`) တစ်ခုပေါင်းထားတဲ့ပုံစံပါ။  
  - แต่ในกรณีนี้ จะต้องเป็น motion ที่ถูกต้อง (ตัวอย่าง: `ysiw`, `ysiW`)

---

#### **3. `ds` (Delete Surround)**
- **`ds` + delimiter**  
  - **Surround ကိုဖျက်မယ်။**
  - ตัวอย่าง:
    - **`ds"`**  
      - Cursor ရဲ့နေရာမှာ surround လုပ်ထားတဲ့ Double Quotes ကို ဖျက်မယ်။
    - **`ds{`**  
      - Surround `{} `ကို ဖျက်မယ်။

#### **4. `cs` (Change Surround)**
- **`cs` + old_delimiter + new_delimiter**  
  - **လက်ရှိ Surround ကိုအသစ်နဲ့ပြောင်းမယ်။**
  - ตัวอย่าง:
    - **`cs"'`**  
      - Surround `" "` ကို `' '` နဲ့ပြောင်းမယ်။
    - **`cs({`**  
      - Surround `( )` ကို `{ }` နဲ့ပြောင်းမယ်။

---

### **သုံးပုံသက်သက်ပြန်ကြည့်ပါ**
#### 1. Surround လုပ်ပုံ (`ys`)
```text
Original: hello world
Command: ysiw"
Result: "hello" world
```

#### 2. Delete Surround (`ds`)
```text
Original: "hello" world
Command: ds"
Result: hello world
```

#### 3. Change Surround (`cs`)
```text
Original: "hello" world
Command: cs"'
Result: 'hello' world
```

---

- **`yst"`** က motion မှားတာလို့ဖြစ်နိုင်တယ်။ Motion သေချာရွေးပါ။
  - **မှန်တဲ့ပုံ:** `ysiW"` (`iw`/`ap`)
- **`ds"`** က Surround ကိုဖျက်တာအလုပ်လုပ်ဖို့ Motion မလိုဘူး။
- **`cs"`** က Surround `" "` ကို `' '` တို့သို့ပြောင်းဖို့အတွက်ပါ။

📝 **မှတ်ချက်:**  
Surround plugin သုံးတဲ့အခါ motion, delimiter တွေမှန်မှသာအလုပ်လုပ်ပါမယ်။ 😍