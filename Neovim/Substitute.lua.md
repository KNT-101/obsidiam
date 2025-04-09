ဒီ code ဟာ Neovim အတွက် **`substitute.nvim`** ဆိုတဲ့ plugin ကို configure လုပ်ဖို့ အသုံးပြုထားတဲ့ Lua script ဖြစ်ပါတယ်။ အဓိကအားဖြင့် **text substitution** လုပ်ငန်းဆောင်တာတွေကို လွယ်ကူစေဖို့ ဒီ plugin ကို အသုံးပြုထားပါတယ်။

### **Code ကို အဆင့်လိုက်ရှင်းပြခြင်း**

```lua
return {
  "gbprod/substitute.nvim",
  event = { "BufReadPre", "BufNewFile" },
  config = function()
    local substitute = require("substitute")

    substitute.setup()

    -- set keymaps
    local keymap = vim.keymap -- for conciseness

    keymap.set("n", "s", substitute.operator, { desc = "Substitute with motion" })
    keymap.set("n", "ss", substitute.line, { desc = "Substitute line" })
    keymap.set("n", "S", substitute.eol, { desc = "Substitute to end of line" })
    keymap.set("x", "s", substitute.visual, { desc = "Substitute in visual mode" })
  end,
}
```

* * *

### **Code Breakdown**

1.  **Plugin Declaration**
    
    ```lua
    return {
      "gbprod/substitute.nvim",
    ```
    
    - ဒီမှာ `substitute.nvim` plugin ကို lazy loading အတွက် အသုံးပြုထားပါတယ်။
    - `"gbprod/substitute.nvim"` မှာ plugin ရဲ့ GitHub URL ကို ဖော်ပြထားတယ်။
2.  **Event-based Loading**
    
    ```lua
    event = { "BufReadPre", "BufNewFile" },
    ```
    
    - **Lazy loading** မျိုးစနစ်ကို သုံးပြီး file ကို ဖတ်မည့်အချိန် (သို့) အသစ်ဖွင့်မည့်အချိန်မှာ plugin ကို load လုပ်မှာဖြစ်တယ်။  
        **`BufReadPre`**: File ဖတ်ရမည့်အချိန်မှာ load လုပ်မယ်။  
        **`BufNewFile`**: File အသစ် ဖန်တီးတဲ့အချိန်မှာ load လုပ်မယ်။
3.  **Plugin Setup**
    
    ```lua
    config = function()
      local substitute = require("substitute")
      substitute.setup()
    ```
    
    - `substitute` module ကို load လုပ်ပြီး **default settings** နဲ့ initialize လုပ်ထားပါတယ်။
4.  **Keymaps Configuration**
    
    ```lua
    local keymap = vim.keymap -- for conciseness
    ```
    
    - Neovim keymap ကို variable အနေနဲ့ သတ်မှတ်ထားပါတယ်။
    
    ```lua
    keymap.set("n", "s", substitute.operator, { desc = "Substitute with motion" })
    ```
    
    - **Normal mode**: `"s"` key ကို motion-based substitution လုပ်ရန် သတ်မှတ်ထားတယ်။  
        **Example**: `sap` ဆိုရင် current position မှ paragraph အထိ substitute လုပ်နိုင်တယ်။
    
    ```lua
    keymap.set("n", "ss", substitute.line, { desc = "Substitute line" })
    ```
    
    - **Normal mode**: `"ss"` ကို current line အတွက် substitution လုပ်ဖို့ သတ်မှတ်ထားတယ်။
    
    ```lua
    keymap.set("n", "S", substitute.eol, { desc = "Substitute to end of line" })
    ```
    
    - **Normal mode**: `"S"` ကို current position မှ line ရဲ့ အဆုံးအထိ substitution လုပ်ဖို့ သတ်မှတ်ထားတယ်။
    
    ```lua
    keymap.set("x", "s", substitute.visual, { desc = "Substitute in visual mode" })
    ```
    
    - **Visual mode**: `"s"` key ကို visual selection အတွင်းမှာ substitution လုပ်ဖို့ သတ်မှတ်ထားတယ်။

* * *

### **အလုပ်လုပ်ပုံ**

1.  **Substitution with Motion (`s`)**
    
    - Normal mode မှာ `"s"` နှိပ်ပြီး motion (e.g., `w`, `p`) တွေသုံးပြီး text area ကို replace လုပ်နိုင်ပါတယ်။
2.  **Substitute Line (`ss`)**
    
    - `"ss"` နှိပ်လိုက်တာနဲ့ အဲဒီ line တစ်ခုလုံးကို replace လုပ်တယ်။
3.  **Substitute to End of Line (`S`)**
    
    - `"S"` ကို current cursor position မှ line ရဲ့ အဆုံးအထိ replace လုပ်တယ်။
4.  **Visual Substitute (`s`)**
    
    - Visual mode မှာ text ကို select လုပ်ပြီး `"s"` နှိပ်လိုက်ရင် selection ထဲမှာသာ replace လုပ်နိုင်တယ်။

ဒီ code ဟာ **`substitute.nvim`** ကို Neovim ထဲမှာ တိုးတက်စွာ အသုံးပြုဖို့ configure လုပ်ထားတဲ့ code ဖြစ်ပါတယ်။ ဒါဟာ motions, lines, visual selections အတွက် replace လုပ်ရတာကို လွယ်ကူပြီး productivity မြင့်စေဖို့ အထူးအသုံးဝင်ပါတယ်။ 

---

### **`substitute.nvim` Plugin မှာ အသုံးပြုနိုင်တဲ့ Keybindings (Note)**  

---

#### **Keybindings**

1. **Normal Mode**
   - `s` → **Substitute with motion**  
     ဥပမာ: `sap` (current position မှ paragraph အထိ replace)
   - `ss` → **Substitute entire line**  
     ဥပမာ: `ss` (line တစ်ကြောင်းလုံး replace)
   - `S` → **Substitute to the end of the line**  
     ဥပမာ: `S` (cursor position မှာနေရာချပြီး အဆုံးထိ replace)

2. **Visual Mode**
   - `s` → **Substitute in selected area**  
     ဥပမာ: Visual mode မှာ text area တစ်ခုကို select လုပ်ပြီး `s` နှိပ်လို့ area ထဲမှာသာ replace လုပ်နိုင်တယ်။

---

#### **Keybindings Summary Table**

| **Mode**       | **Keybinding** | **Description**                |
|-----------------|---------------|--------------------------------|
| Normal          | `s`           | Substitute with motion         |
| Normal          | `ss`          | Substitute entire line         |
| Normal          | `S`           | Substitute to end of line      |
| Visual          | `s`           | Substitute in visual selection |

---

#### **လုပ်ဆောင်ပုံ (Examples)**

1. **Substitute with Motion (`s`)**
   ```text
   Cursor: The quick brown fox jumps over the lazy dog
   Command: sap
   Result: The quick brown [replacement_text] over the lazy dog
   ```
   - `sap` ဆိုတာ current position မှ paragraph အထိ text ကို replace လုပ်တယ်။

2. **Substitute Entire Line (`ss`)**
   ```text
   Original Line: The quick brown fox
   Command: ss
   Result: [replacement_text]
   ```
   - Line တစ်ကြောင်းလုံးကို အစားထိုးတယ်။

3. **Substitute to End of Line (`S`)**
   ```text
   Cursor: The quick |brown fox jumps over the lazy dog
   Command: S
   Result: The quick [replacement_text]
   ```
   - Cursor ရှိတဲ့နေရာကနေ အဆုံးအထိ အစားထိုးတယ်။

4. **Visual Substitute (`s`)**
   ```text
   Selection: brown fox
   Command: s
   Result: [replacement_text]
   ```
   - Visual mode မှာ `brown fox` ကို select လုပ်ပြီး replace လုပ်တယ်။

---

#### **အသုံးပြုနိုင်တဲ့ Tips**
1. **Preview Replacement**  
   Replace လုပ်မယ့်အချိန်မှာ preview ကိုဖတ်နိုင်ဖို့ `substitute.nvim` plugin ကို setup မှာ preview options ထည့်နိုင်တယ်။

2. **Undo Support**  
   Replace လုပ်ပြီးနောက် `u` ကိုသုံးပြီး undo လုပ်နိုင်တယ်။

3. **Custom Keymaps**  
   Default keybindings မကြိုက်ရင် `keymap.set()` မှာ သင့်တော်တဲ့ keys ပြောင်းနိုင်တယ်။

---
# **Substitute.nvim Plugin အသုံးပြုပုံကို စနစ်တကျ Note**

---

### **Substitute.nvim Plugin**

**Substitute.nvim** ဟာ **Neovim** အတွက် text replacement ကို လွယ်ကူစွာ လုပ်ဆောင်နိုင်စေဖို့ ရည်ရွယ်ထားတဲ့ plugin တစ်ခုဖြစ်ပါတယ်။

---

### **Keybindings နဲ့ အသုံးပြုပုံ**

| **Mode**       | **Keybinding** | **Description**                                   | **အသုံးပြုပုံ**                                                                                              |
|-----------------|---------------|---------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| **Normal**      | `s`           | Substitute with motion                           | 1. Cursor ကို start position မှာထားပါ။  <br> 2. `s` နှိပ်ပြီး motion (`w`, `p`) သုံးပါ။ <br> *ဥပမာ*: `sap` (cursor မှ paragraph အထိ replace) |
| **Normal**      | `ss`          | Substitute entire line                           | Cursor ကို လိုချင်တဲ့ line မှာထားပြီး `ss` နှိပ်ပါ။ <br> *ဥပမာ*: `ss` (line တစ်ကြောင်းလုံး replace)                              |
| **Normal**      | `S`           | Substitute to end of line                        | Cursor ကို start position မှာထားပြီး `S` နှိပ်ပါ။ <br> *ဥပမာ*: `S` (cursor position မှာနေရာချပြီး အဆုံးထိ replace)                 |
| **Visual**      | `s`           | Substitute in selected area                      | Visual mode ကိုသုံးပြီး text ကို select လုပ်ပါ။ <br> `s` ကိုနှိပ်ပြီး replacement လုပ်ပါ။                                           |

---

### **အသုံးပြုရန် လုပ်ဆောင်ချက်များ**

#### 1. **Substitute with Motion (Normal Mode - `s`)**
   - **အသုံးပြုပုံ:**
     1. Cursor ကို start position မှာထားပါ။
     2. `s` နှိပ်ပြီး motion (ဥပမာ: `w`, `p`) သုံးပါ။
     3. Replace လုပ်မယ့် text ကို type လုပ်ပြီး enter နှိပ်ပါ။
   - **ဥပမာ:**
     ```text
     The quick brown fox jumps over the lazy dog
     ```
     Cursor ကို **"quick"** မှာထားပြီး `sap` ကို type လုပ်ပါ။  
     ```text
     The [replacement_text] jumps over the lazy dog
     ```

#### 2. **Substitute Entire Line (Normal Mode - `ss`)**
   - **အသုံးပြုပုံ:**
     1. Cursor ကို သင့်တော်တဲ့ line မှာထားပါ။
     2. `ss` ကိုနှိပ်ပြီး replacement လုပ်မယ့် text ကို type လုပ်ပါ။
   - **ဥပမာ:**
     ```text
     The quick brown fox
     ```
     Cursor ကို စတန်းတစ်ကြောင်းမှာထားပြီး `ss` နှိပ်ပါ။  
     ```text
     [replacement_text]
     ```

#### 3. **Substitute to End of Line (Normal Mode - `S`)**
   - **အသုံးပြုပုံ:**
     1. Cursor ကို start position မှာထားပါ။
     2. `S` ကိုနှိပ်ပြီး replacement text ကို type လုပ်ပါ။
   - **ဥပမာ:**
     ```text
     The quick brown fox jumps over the lazy dog
     ```
     Cursor ကို **"brown"** မှာထားပြီး `S` ကို type လုပ်ပါ။  
     ```text
     The quick [replacement_text]
     ```

#### 4. **Substitute in Selected Area (Visual Mode - `s`)**
   - **အသုံးပြုပုံ:**
     1. Visual mode (Press `v`) ကိုသုံးပြီး replace လုပ်ချင်တဲ့ area ကို select လုပ်ပါ။
     2. `s` ကိုနှိပ်ပြီး replacement text ကို type လုပ်ပါ။
   - **ဥပမာ:**
     ```text
     The quick brown fox jumps over the lazy dog
     ```
     Visual mode နဲ့ **"brown fox"** ကို select လုပ်ပြီး `s` နှိပ်ပါ။  
     ```text
     The quick [replacement_text] jumps over the lazy dog
     ```

---

### **အသုံးဝင်သော Features**
1. **Undo Support**
   - Replacement လုပ်ပြီးနောက် `u` သုံးပြီး ပြန်ပြင်လို့ရတယ်။

2. **Preview Options**
   - Replacement လုပ်မယ့်အချိန်မှာ preview တွေပြဖို့ settings တွေကို အသုံးပြုနိုင်တယ်။

3. **Custom Keybindings**
   - Default keys မကြိုက်ရင် `keymap.set()` ကို သုံးပြီး keys ကိုပြောင်းနိုင်တယ်။

---

