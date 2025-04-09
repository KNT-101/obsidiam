
`surround.lua` ဖိုင်ထဲမှာပါတဲ့ code က LazyVim မှာ `nvim-surround` plugin ကို ထည့်သွင်းဖို့ အသုံးပြုတဲ့ configuration file တစ်ခုဖြစ်ပါတယ်။ ဒီ plugin ဟာ text တွေကို surround (ပတ်ဝန်းကျင်မှာ သက်ဆိုင်ရာ syntax တွေဖြည့်တာ) လုပ်နိုင်အောင် အထောက်အပံ့ပေးပါတယ်။ 

ဒီ code ရဲ့ လုပ်ဆောင်ချက်တွေကိုအောက်မှာရှင်းပြပေးမယ်နော်။

---

### **Code Breakdown**

```lua
return {
  "kylechui/nvim-surround", -- Plugin repository URL
  event = { "BufReadPre", "BufNewFile" }, -- Plugin ကို သတ်မှတ်ထားတဲ့ event တွေအပေါ် မှီခိုပြီး load လုပ်မယ်
  version = "*", -- Stability အတွက် လက်ရှိ stable version ကို သုံးမယ်
  config = true, -- Default configuration ကို enable လုပ်မယ်
}
```

#### **လုပ်ဆောင်မှုများ**
1. **Plugin Repository**:  
   - `"kylechui/nvim-surround"` ဆိုတာက GitHub repository URL ကို ပြောတာဖြစ်ပြီး ဒီ plugin ကို Lazy.nvim မှတစ်ဆင့် install လုပ်မယ်။  
   - Example: https://github.com/kylechui/nvim-surround  

2. **Event-Driven Loading**:
   - `event = { "BufReadPre", "BufNewFile" }` ဆိုတာက **Lazy Loading** ကိုပြုလုပ်တာပါ။
   - **BufReadPre**: ဖိုင်တစ်ခုကို ဖွင့်ခါစမှာ plugin ကို load လုပ်မယ်။
   - **BufNewFile**: ဖိုင်အသစ်တစ်ခုကို ဖန်တီးတဲ့အခါ load လုပ်မယ်။
   - ဒီလိုလုပ်ထားတာက performance အတွက် အထောက်အပံ့ပေးတာပါ။

3. **Version**:
   - `version = "*"` ဆိုတာက stable version ကိုသုံးဖို့ ဆိုလိုတာပါ။
   - ဒီလိုသတ်မှတ်ထားတာက ပိုပြီးစိတ်ချရတဲ့ feature တွေကို ရဖို့ပါ။
   - `main` branch ကို သုံးချင်ရင် `version` key ကို ဖျက်လို့ရတယ်။

4. **Config**:
   - `config = true` ဆိုတာက plugin ရဲ့ default settings ကို enable လုပ်တာပါ။
   - Default settings တွေကို မလိုချင်ရင်၊ သင့်မိမိ settings တွေထည့်ချင်ရင် `config` ကို function ပုံစံဖြင့်ရေးနိုင်ပါတယ်။

---

### **nvim-surround Plugin လုပ်ဆောင်ချက်များ**
`nvim-surround` plugin ကို အသုံးပြုရင်း Text Surrounding အလုပ်လုပ်ဆောင်နိုင်ပါတယ်။

- **အဓိက Feature**:  
  - Text, words, or blocks of code တွေကို delimiter (e.g., `()` ၊ `{}` ၊ `""` စသဖြင့်) အသုံးပြုပြီး surround လုပ်နိုင်မယ်။
  - အရင် surround ထည့်ထားတဲ့ text တွေကို replace, delete, change လုပ်နိုင်မယ်။

- **Shortcut Keys (Default)**:
  - Add Surround: `ys<motion><delimiter>`  
    - Example: `ysiw"` → Word တစ်လုံးကို `"` နဲ့ surround လုပ်မယ်။
  - Change Surround: `cs<old><new>`  
    - Example: `cs"'` → `"` surround ကို `'` surround ပြောင်းမယ်။
  - Delete Surround: `ds<delimiter>`  
    - Example: `ds"` → `"` surround ကိုဖျက်မယ်။

---

### **Custom Configuration Example**
Default settings တွေမလိုချင်လို့ customize လုပ်ချင်ရင် `config` ကို function ပုံစံဖြင့်ရေးနိုင်တယ်။

```lua
return {
  "kylechui/nvim-surround",
  event = { "BufReadPre", "BufNewFile" },
  config = function()
    require("nvim-surround").setup({
      surrounds = {
        ["("] = { add = { "(", ")" } },
        ["{"] = { add = { "{", "}" } },
        ["["] = { add = { "[", "]" } },
      },
    })
  end,
}
```

ဒီလိုရေးလိုက်ရင် surround delimiter တွေကို ကိုယ်ပိုင်စိတ်ကြိုက်ပြင်နိုင်မယ်။

---
---

**nvim-surround** ဟာ Text, Word, Paragraph စတာတွေကို surround လုပ်ဖို့ အသုံးပြုတဲ့ tool ဖြစ်ပြီး အလွယ်တကူ **add**, **delete**, **replace** လုပ်နိုင်ပါတယ်။

---

### **1. Add Surround**
Text ကို surround လုပ်ဖို့ (e.g., `()` ၊ `{}` ၊ `""` စသဖြင့်) သုံးနိုင်ပါတယ်။

#### Syntax:
```plaintext
ys<motion><delimiter>
```

- **ys** → Yank Surround လုပ်မယ်။
- **<motion>** → Target Text/Word ကို သတ်မှတ်ဖို့ (e.g., `iw` for "inside word")။
- **<delimiter>** → Surround Type (e.g., `"` ၊ `[` ၊ `{` ၊ `)` )။

#### Examples:
1. **Word ကို Quotation Mark နဲ့ surround လုပ်မယ်**  
   - **Before**: `hello world`  
   - **Command**: `ysiw"`  
   - **After**: `"hello" world`

2. **Line တစ်ကြောင်းကို Parentheses နဲ့ surround လုပ်မယ်**  
   - **Before**: `print "hello"`  
   - **Command**: `yss(`  
   - **After**: `(print "hello")`

---

### **2. Delete Surround**
အရင် surround ထည့်ထားတဲ့ delimiter (e.g., `()` ၊ `{}` ၊ `""`) ကို ဖျက်ချင်ရင် သုံးနိုင်ပါတယ်။

#### Syntax:
```plaintext
ds<delimiter>
```

- **ds** → Delete Surround.
- **<delimiter>** → ဖျက်လိုတဲ့ Surround Type.

#### Examples:
1. **Quotation Mark ကိုဖျက်မယ်**  
   - **Before**: `"hello"`  
   - **Command**: `ds"`  
   - **After**: `hello`

2. **Parentheses ကိုဖျက်မယ်**  
   - **Before**: `(print "hello")`  
   - **Command**: `ds(`  
   - **After**: `print "hello"`

---

### **3. Change Surround**
တစ်ခုခု surround ထည့်ထားတာကို **အခြား delimiter** တစ်ခုကို ပြောင်းချင်ရင် သုံးနိုင်ပါတယ်။

#### Syntax:
```plaintext
cs<old><new>
```

- **cs** → Change Surround.
- **<old>** → မူလ Surround Type.
- **<new>** → အသစ် surround လုပ်မယ့် Type.

#### Examples:
1. **Quotation Mark ကို Parentheses ပြောင်းမယ်**  
   - **Before**: `"hello"`  
   - **Command**: `cs"'`  
   - **After**: `'hello'`

2. **Parentheses ကို Curly Braces ပြောင်းမယ်**  
   - **Before**: `(print "hello")`  
   - **Command**: `cs({`  
   - **After**: `{print "hello"}`

---

### **4. Visual Mode Usage**
Surround လုပ်ချင်တဲ့ text ကို **visual mode** နဲ့ရွေးပြီး surround လုပ်နိုင်ပါတယ်။

#### Steps:
1. Visual mode (select text): Press `v` and select the text.
2. Surround: Press `S` followed by the delimiter.

#### Example:
- **Before**: `hello world`  
- **Visual Select**: `hello`  
- **Command**: `S"`  
- **After**: `"hello" world`

---

### **5. Advanced Usage**
- **Tag Surround**:
  - Syntax: `yst<tag>`
  - Example:  
    - **Before**: `hello`  
    - **Command**: `ystb`  
    - **After**: `<b>hello</b>`

- **Multi-line Surround**:
  - Use motion (e.g., `yS}` for a paragraph) to wrap multiple lines with `{}`.

---

### **Commands Recap** (Note အတွက် 📝)
| Command        | Description                          | Example Input         | Example Output         |
|----------------|--------------------------------------|-----------------------|-------------------------|
| `ys<motion><delimiter>` | Add surround                  | `ysiw"`              | `"word"`               |
| `yss<delimiter>` | Add surround to the whole line      | `yss(`               | `(line content)`       |
| `ds<delimiter>` | Delete surround                     | `ds"`                | `word`                 |
| `cs<old><new>` | Change surround                     | `cs"'`               | `'word'`               |
| `v + S<delimiter>` | Visual mode surround              | Select text + `S"`   | `"selected text"`      |

---

