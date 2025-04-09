
Neovim config ထဲမှာ **text ထဲက စာသားတွေကို ဖျက်ဖို့** အောက်ပါ keymaps တွေကို အသုံးပြုနိုင်ပါတယ်။ ဒီ keymaps တွေက Vim/Neovim ရဲ့ built-in features တွေဖြစ်ပြီး၊ plugin မလိုဘဲ အသုံးပြုနိုင်ပါတယ်။

---

## **Text ထဲက စာသားတွေကို ဖျက်နည်း**:

### **1. Word တစ်ခုလုံးကို ဖျက်ဖို့**:
- **`diw`**:
  - **Mode**: Normal mode
  - **Action**: Delete inside word.
  - **Description**: Cursor ရှိတဲ့ word တစ်ခုလုံးကို ဖျက်ပါ။
  - **ဥပမာ**: `hello world` ထဲမှာ `hello` ပေါ်မှာ cursor ရှိရင် `diw` နှိပ်ပါက `hello` ကို ဖျက်ပြီး `world` ပဲ ကျန်ပါလိမ့်မယ်။

---

### **2. Quotes ထဲက စာသားတွေကို ဖျက်ဖို့**:
- **`di"`**:
  - **Mode**: Normal mode
  - **Action**: Delete inside double quotes.
  - **Description**: Double quotes (`"`) ထဲက စာသားတွေကို ဖျက်ပါ။
  - **ဥပမာ**: `"hello world"` ထဲမှာ cursor ရှိရင် `di"` နှိပ်ပါက `hello world` ကို ဖျက်ပြီး `""` ပဲ ကျန်ပါလိမ့်မယ်။

- **`di'`**:
  - **Mode**: Normal mode
  - **Action**: Delete inside single quotes.
  - **Description**: Single quotes (`'`) ထဲက စာသားတွေကို ဖျက်ပါ။
  - **ဥပမာ**: `'hello world'` ထဲမှာ cursor ရှိရင် `di'` နှိပ်ပါက `hello world` ကို ဖျက်ပြီး `''` ပဲ ကျန်ပါလိမ့်မယ်။

---

### **3. Parentheses ထဲက စာသားတွေကို ဖျက်ဖို့**:
- **`di(`** or **`di)`**:
  - **Mode**: Normal mode
  - **Action**: Delete inside parentheses.
  - **Description**: Parentheses (`()`) ထဲက စာသားတွေကို ဖျက်ပါ။
  - **ဥပမာ**: `(hello world)` ထဲမှာ cursor ရှိရင် `di(` နှိပ်ပါက `hello world` ကို ဖျက်ပြီး `()` ပဲ ကျန်ပါလိမ့်မယ်။

---

### **4. Curly Braces ထဲက စာသားတွေကို ဖျက်ဖို့**:
- **`di{`** or **`di}`**:
  - **Mode**: Normal mode
  - **Action**: Delete inside curly braces.
  - **Description**: Curly braces (`{}`) ထဲက စာသားတွေကို ဖျက်ပါ။
  - **ဥပမာ**: `{hello world}` ထဲမှာ cursor ရှိရင် `di{` နှိပ်ပါက `hello world` ကို ဖျက်ပြီး `{}` ပဲ ကျန်ပါလိမ့်မယ်။

---

### **5. Square Brackets ထဲက စာသားတွေကို ဖျက်ဖို့**:
- **`di[`** or **`di]`**:
  - **Mode**: Normal mode
  - **Action**: Delete inside square brackets.
  - **Description**: Square brackets (`[]`) ထဲက စာသားတွေကို ဖျက်ပါ။
  - **ဥပမာ**: `[hello world]` ထဲမှာ cursor ရှိရင် `di[` နှိပ်ပါက `hello world` ကို ဖျက်ပြီး `[]` ပဲ ကျန်ပါလိမ့်မယ်။

---

### **6. Tags ထဲက စာသားတွေကို ဖျက်ဖို့**:
- **`dit`**:
  - **Mode**: Normal mode
  - **Action**: Delete inside HTML/XML tags.
  - **Description**: HTML/XML tags (`<tag>...</tag>`) ထဲက စာသားတွေကို ဖျက်ပါ။
  - **ဥပမာ**: `<div>hello world</div>` ထဲမှာ cursor ရှိရင် `dit` နှိပ်ပါက `hello world` ကို ဖျက်ပြီး `<div></div>` ပဲ ကျန်ပါလိမ့်မယ်။

---

### **7. Line တစ်ခုလုံးကို ဖျက်ဖို့**:
- **`dd`**:
  - **Mode**: Normal mode
  - **Action**: Delete the current line.
  - **Description**: Cursor ရှိတဲ့ line တစ်ခုလုံးကို ဖျက်ပါ။
  - **ဥပမာ**: `hello world` ထဲမှာ cursor ရှိရင် `dd` နှိပ်ပါက line တစ်ခုလုံး ဖျက်သွားပါလိမ့်မယ်။

---

### **8. Visual Mode မှာ ဖျက်ဖို့**:
- **`v` + `motion` + `d`**:
  - **Mode**: Visual mode
  - **Action**: Select text and delete.
  - **Description**: Visual mode မှာ text တွေကို select လုပ်ပြီး ဖျက်ပါ။
  - **ဥပမာ**:
    - `v` နှိပ်ပြီး text တွေကို select လုပ်ပါ။
    - `d` နှိပ်ပြီး ဖျက်ပါ။

---

### **မှတ်ချက်**:
- **အဆင်ပြေပါတယ်**။ ဒီ keymaps တွေကို မှန်ကန်စွာ အသုံးပြုပါက text ထဲက စာသားတွေကို အလွယ်တကူ ဖျက်နိုင်ပါပီ။
---

