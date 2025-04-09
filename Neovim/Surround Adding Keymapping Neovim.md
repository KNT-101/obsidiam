

## 1️⃣ **Surround Adding (`ys`)**
**Syntax:** `ys<motion><char>`

| Keymap   | Description |
|----------|------------|
| `ysiw"`  | **"word"** (word ကို double quotes ဝိုင်းမယ်) |
| `ysiW'`  | **'long word'** (whole word ကို single quotes ဝိုင်းမယ်) |
| `ysip(`  | **(This is a sentence.)** (paragraph ကို parentheses ဝိုင်းမယ်) |
| `yss"`  | **"This is a full line."** (စာကြောင်းတစ်ကြောင်းလုံးကို quotes ဝိုင်းမယ်) |
| `ySS(`  | **(This is a full line.)** (စာကြောင်းကို parentheses ဝိုင်းပြီး newline ထည့်မယ်) |
| `ysiw[`  | **[word]** (square brackets ဝိုင်းမယ်) |
| `ysiw{`  | **{word}** (curly brackets ဝိုင်းမယ်) |
| `ysiw<`  | **<word>** (angle brackets ဝိုင်းမယ်) |
| `yswi`\<enter\> | write current cursor insert word duble enter mode | 

---

## 2️⃣ **Surround Deleting (`ds`)**
**Syntax:** `ds<char>`

| Keymap  | Description |
|---------|------------|
| `ds"`  | **"word" → word** (double quotes ကိုဖျက်မယ်) |
| `ds'`  | **'word' → word** (single quotes ကိုဖျက်မယ်) |
| `ds(`  | **(word) → word** (parentheses ကိုဖျက်မယ်) |
| `ds[`  | **[word] → word** (square brackets ကိုဖျက်မယ်) |
| `ds{`  | **{word} → word** (curly brackets ကိုဖျက်မယ်) |
| `ds<`  | **<word> → word** (angle brackets ကိုဖျက်မယ်) |

---

## 3️⃣ **Surround Changing (`cs`)**
**Syntax:** `cs<old><new>`

| Keymap  | Description |
|---------|------------|
| `cs"'`  | **"word" → 'word'** (double quotes ကို single quotes ပြောင်းမယ်) |
| `cs([`  | **(word) → [word]** (parentheses ကို square brackets ပြောင်းမယ်) |
| `cs'"`  | **'word' → "word"** (single quotes ကို double quotes ပြောင်းမယ်) |
| `cs({`  | **(word) → {word}** (parentheses ကို curly brackets ပြောင်းမယ်) |
| `cs<"`  | **<word> → "word"** (angle brackets ကို double quotes ပြောင်းမယ်) |

---

## 4️⃣ **Visual Mode Surround (`S`)**
**Syntax:** `S<char>`

| Keymap  | Description |
|---------|------------|
| `S"`  | **"selected word"** (Visual mode မှာ select လုပ်ပြီး surround) |
| `S{`  | **{selected sentence}** (Visual mode မှာ select လုပ်ပြီး surround) |
| `S(`  | **(selected text)** (parentheses နဲ့ surround) |
| `S[`  | **[selected text]** (square brackets နဲ့ surround) |

---

## 5️⃣ **Line Surround (`yss`)**
**Syntax:** `yss<char>`

| Keymap  | Description |
|---------|------------|
| `yss"`  | **"This is a full line."** |
| `yss(`  | **(This is a full line.)** |
| `yss{`  | **{This is a full line.}** |
| `yss[`  | **[This is a full line.]** |

---

## 6️⃣ **Multiple Lines Surround (`yS`)**
**Syntax:** `yS<motion><char>`

| Keymap  | Description |
|---------|------------|
| `yS}`  | **{ Line 1\nLine 2\nLine 3 }** (Multiple lines ကို braces ဝိုင်းမယ်) |
| `yS)`  | **( Line 1\nLine 2\nLine 3 )** (Multiple lines ကို parentheses ဝိုင်းမယ်) |
| `yS]`  | **[ Line 1\nLine 2\nLine 3 ]** (Multiple lines ကို square brackets ဝိုင်းမယ်) |
| `yS> ` | **< Line 1\nLine 2\nLine 3 >** (Multiple lines ကို angle brackets ဝိုင်းမယ်) |

---


## **Neovim Text Deletion Keymaps**

| **Keymap**  | **Mode** | **Action** | **Description** |
|------------|---------|-----------|----------------|
| `diw` | Normal | Delete inside word | Cursor ရှိတဲ့ word တစ်ခုလုံးကို ဖျက်ပါ။ |
| `di"` | Normal | Delete inside double quotes | `""` ထဲက စာသားတွေကို ဖျက်ပြီး `""` ပဲကျန်ပါမယ်။ |
| `di'` | Normal | Delete inside single quotes | `''` ထဲက စာသားတွေကို ဖျက်ပြီး `''` ပဲကျန်ပါမယ်။ |
| `di(` or `di)` | Normal | Delete inside parentheses | `()` ထဲက စာသားတွေကို ဖျက်ပြီး `()` ပဲကျန်ပါမယ်။ |
| `di{` or `di}` | Normal | Delete inside curly braces | `{}` ထဲက စာသားတွေကို ဖျက်ပြီး `{}` ပဲကျန်ပါမယ်။ |
| `di[` or `di]` | Normal | Delete inside square brackets | `[]` ထဲက စာသားတွေကို ဖျက်ပြီး `[]` ပဲကျန်ပါမယ်။ |
| `dit` | Normal | Delete inside HTML/XML tags | `<tag>...</tag>` ထဲက စာသားတွေကို ဖျက်ပြီး `<tag></tag>` ပဲကျန်ပါမယ်။ |
| `dd` | Normal | Delete the current line | Cursor ရှိတဲ့ line တစ်ခုလုံးကို ဖျက်ပါ။ |
| `v` + `motion` + `d` | Visual | Select and delete | Visual mode မှာ select လုပ်ပြီး ဖျက်ပါ။ |

---



### **1\. General Keymaps**:

| Keymap       | Mode          | Action                      | Description |
|-------------|--------------|-----------------------------|-------------|
| `jk`       | Insert       | Exit insert mode            | Insert mode ကနေ Normal mode ကို ပြန်ထွက်ဖို့။ |
| `<leader>nh` | Normal      | Clear search highlights    | Search highlight တွေကို ဖျက်ဖို့။ |

---

### **2\. Terminal Keymaps**:

| Keymap       | Mode          | Action                      | Description |
|-------------|--------------|-----------------------------|-------------|
| `<leader>tt` | Normal      | Toggle terminal            | Terminal ကို ဖွင့်/ပိတ် လုပ်ဖို့။ |
| `<esc>`     | Terminal     | Exit terminal mode         | Terminal mode ကနေ Normal mode ကို ပြန်ထွက်ဖို့။ |
| `<C-h>`     | Terminal     | Move to left window        | Terminal ထဲမှာ ဘယ်ဘက် window ကို ရွှေ့ဖို့။ |
| `<C-j>`     | Terminal     | Move to bottom window      | Terminal ထဲမှာ အောက်ဘက် window ကို ရွှေ့ဖို့။ |
| `<C-k>`     | Terminal     | Move to top window         | Terminal ထဲမှာ အပေါ်ဘက် window ကို ရွှေ့ဖို့။ |
| `<C-l>`     | Terminal     | Move to right window       | Terminal ထဲမှာ ညာဘက် window ကို ရွှေ့ဖို့။ |

---

### **3\. Window Management Keymaps**:

| Keymap       | Mode          | Action                      | Description |
|-------------|--------------|-----------------------------|-------------|
| `<leader>sv` | Normal      | Split window vertically    | Window ကို vertically split လုပ်ဖို့။ |
| `<leader>sh` | Normal      | Split window horizontally  | Window ကို horizontally split လုပ်ဖို့။ |
| `<leader>se` | Normal      | Make splits equal size     | Split windows တွေကို အရွယ်အစား တူညီအောင် ပြင်ဖို့။ |
| `<leader>sx` | Normal      | Close current split        | လက်ရှိ split window ကို ပိတ်ဖို့။ |

---

### **4\. Tab Management Keymaps**:

| Keymap       | Mode          | Action                      | Description |
|-------------|--------------|-----------------------------|-------------|
| `<leader>to` | Normal      | Open new tab               | Tab အသစ်ဖွင့်ဖို့။ |
| `<leader>tx` | Normal      | Close current tab          | လက်ရှိ tab ကို ပိတ်ဖို့။ |
| `<leader>tn` | Normal      | Go to next tab             | နောက် tab ကို သွားဖို့။ |
| `<leader>tp` | Normal      | Go to previous tab         | ရှေ့ tab ကို သွားဖို့။ |
| `<leader>tf` | Normal      | Open current buffer in new tab | လက်ရှိ buffer ကို tab အသစ်မှာ ဖွင့်ဖို့။ |

---

### **5\. Number Increment/Decrement Keymaps**:

| Keymap       | Mode          | Action                      | Description |
|-------------|--------------|-----------------------------|-------------|
| `<leader>+` | Normal      | Increment number           | Number တွေကို တိုးဖို့။ |
| `<leader>-` | Normal      | Decrement number           | Number တွေကို လျှော့ဖို့။ |

---

### **6\. Other Keymaps**:

| Keymap       | Mode          | Action                      | Description |
|-------------|--------------|-----------------------------|-------------|
| `<leader>ff` | Normal      | Find files with Telescope  | Files တွေကို fuzzy finder နဲ့ ရှာဖို့။ |
| `<leader>fg` | Normal      | Live grep with Telescope   | Text တွေကို live grep နဲ့ ရှာဖို့။ |
| `<leader>fb` | Normal      | Find buffers with Telescope | Buffers တွေကို ရှာဖို့။ |

---

### **7\. Visual Mode Keymaps**:

| Keymap       | Mode          | Action                      | Description |
|-------------|--------------|-----------------------------|-------------|
| `vw`       | Visual       | Select word                | Cursor position ကနေ word တစ်လုံးကို ရွေးရန်။ |
| `vwy`      | Visual       | Copy selected word         | Cursor position ကနေ word တစ်လုံးကို ကူးရန်။ |

---

### **8\. Surround Keymaps**:

| Keymap       | Mode          | Action                      | Description |
|-------------|--------------|-----------------------------|-------------|
| `yswi`     | Normal       | Add surrounding delimiters | Cursor current word ကို အဝိုင်း၊ `"` ၊ `'` စသည်ဖြင့် ဝိုင်းလိုက်နိုင်သည်။ |

---

### **အသုံးပြုနည်း**:

#### **Terminal**
- `<leader>tt` → Terminal ဖွင့်ပါ။
- `<esc>` → Terminal mode မှ ထွက်ပါ။

#### **Window Management**
- `<leader>sv` → Window ကို vertically split လုပ်ပါ။
- `<leader>sh` → Window ကို horizontally split လုပ်ပါ။

#### **Tab Management**
- `<leader>to` → Tab အသစ်ဖွင့်ပါ။
- `<leader>tx` → Tab ပိတ်ပါ။

#### **Number Increment/Decrement**
- `<leader>+` → Number တွေကို တိုးပါ။
- `<leader>-` → Number တွေကို လျှော့ပါ။

#### **Surround Keymaps**
- `yswi"` → Word တစ်ခုကို `"` ထည့်ခြင်း။
- `yswi'` → Word တစ်ခုကို `'` ထည့်ခြင်း။

---

