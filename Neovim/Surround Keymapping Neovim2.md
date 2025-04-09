
**vim-surround Keymaps Full Note**

---

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

