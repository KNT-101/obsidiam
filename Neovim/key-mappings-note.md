
ဟုတ်ကဲ့! သင့်ရဲ့ Neovim config ထဲက **key mappings တွေကို note နဲ့တကွ** ရှင်းပြပေးပါမယ်။ ဒီမှာ သင့်အတွက် အသေးစိတ် ရှင်းလင်းချက်ပါ။

* * *

## **Key Mappings များ**:

### **1\. General Keymaps**:

- **`jk`**:
    
    - **Mode**: Insert mode
    - **Action**: Exit insert mode.
    - **Description**: Insert mode ကနေ Normal mode ကို ပြန်ထွက်ဖို့။
- **`<leader>nh`**:
    
    - **Mode**: Normal mode
    - **Action**: Clear search highlights.
    - **Description**: Search highlight တွေကို ဖျက်ဖို့။

* * *

### **2\. Terminal Keymaps**:

- **`<leader>tt`**:
    
    - **Mode**: Normal mode
    - **Action**: Toggle terminal.
    - **Description**: Terminal ကို ဖွင့်/ပိတ် လုပ်ဖို့။
- **`<esc>`**:
    
    - **Mode**: Terminal mode
    - **Action**: Exit terminal mode.
    - **Description**: Terminal mode ကနေ Normal mode ကို ပြန်ထွက်ဖို့။
- **`<C-h>`**:
    
    - **Mode**: Terminal mode
    - **Action**: Move to left window.
    - **Description**: Terminal ထဲမှာ ဘယ်ဘက် window ကို ရွှေ့ဖို့။
- **`<C-j>`**:
    
    - **Mode**: Terminal mode
    - **Action**: Move to bottom window.
    - **Description**: Terminal ထဲမှာ အောက်ဘက် window ကို ရွှေ့ဖို့။
- **`<C-k>`**:
    
    - **Mode**: Terminal mode
    - **Action**: Move to top window.
    - **Description**: Terminal ထဲမှာ အပေါ်ဘက် window ကို ရွှေ့ဖို့။
- **`<C-l>`**:
    
    - **Mode**: Terminal mode
    - **Action**: Move to right window.
    - **Description**: Terminal ထဲမှာ ညာဘက် window ကို ရွှေ့ဖို့။

* * *

### **3\. Window Management Keymaps**:

- **`<leader>sv`**:
    
    - **Mode**: Normal mode
    - **Action**: Split window vertically.
    - **Description**: Window ကို vertically split လုပ်ဖို့။
- **`<leader>sh`**:
    
    - **Mode**: Normal mode
    - **Action**: Split window horizontally.
    - **Description**: Window ကို horizontally split လုပ်ဖို့။
- **`<leader>se`**:
    
    - **Mode**: Normal mode
    - **Action**: Make splits equal size.
    - **Description**: Split windows တွေကို အရွယ်အစား တူညီအောင် ပြင်ဖို့။
- **`<leader>sx`**:
    
    - **Mode**: Normal mode
    - **Action**: Close current split.
    - **Description**: လက်ရှိ split window ကို ပိတ်ဖို့။

* * *

### **4\. Tab Management Keymaps**:

- **`<leader>to`**:
    
    - **Mode**: Normal mode
    - **Action**: Open new tab.
    - **Description**: Tab အသစ်ဖွင့်ဖို့။
- **`<leader>tx`**:
    
    - **Mode**: Normal mode
    - **Action**: Close current tab.
    - **Description**: လက်ရှိ tab ကို ပိတ်ဖို့။
- **`<leader>tn`**:
    
    - **Mode**: Normal mode
    - **Action**: Go to next tab.
    - **Description**: နောက် tab ကို သွားဖို့။
- **`<leader>tp`**:
    
    - **Mode**: Normal mode
    - **Action**: Go to previous tab.
    - **Description**: ရှေ့ tab ကို သွားဖို့။
- **`<leader>tf`**:
    
    - **Mode**: Normal mode
    - **Action**: Open current buffer in new tab.
    - **Description**: လက်ရှိ buffer ကို tab အသစ်မှာ ဖွင့်ဖို့။

* * *

### **5\. Number Increment/Decrement Keymaps**:

- **`<leader>+`**:
    
    - **Mode**: Normal mode
    - **Action**: Increment number.
    - **Description**: Number တွေကို တိုးဖို့။
- **`<leader>-`**:
    
    - **Mode**: Normal mode
    - **Action**: Decrement number.
    - **Description**: Number တွေကို လျှော့ဖို့။

* * *

### **6\. Other Keymaps**:

- **`<leader>ff`**:
    
    - **Mode**: Normal mode
    - **Action**: Find files with Telescope.
    - **Description**: Files တွေကို fuzzy finder နဲ့ ရှာဖို့။
- **`<leader>fg`**:
    
    - **Mode**: Normal mode
    - **Action**: Live grep with Telescope.
    - **Description**: Text တွေကို live grep နဲ့ ရှာဖို့။
- **`<leader>fb`**:
    
    - **Mode**: Normal mode
    - **Action**: Find buffers with Telescope.
    - **Description**: Buffers တွေကို ရှာဖို့။

* * *

### **အသုံးပြုနည်း**:

1.  **Terminal**:
    
    - `<leader>tt`: Terminal ဖွင့်ပါ။
    - `<esc>`: Terminal ကနေ ထွက်ပါ။
2.  **Window Management**:
    
    - `<leader>sv`: Window ကို vertically split လုပ်ပါ။
    - `<leader>sh`: Window ကို horizontally split လုပ်ပါ။
3.  **Tab Management**:
    
    - `<leader>to`: Tab အသစ်ဖွင့်ပါ။
    - `<leader>tx`: Tab ပိတ်ပါ။
4.  **Number Increment/Decrement**:
    
    - `<leader>+`: Number တွေကို တိုးပါ။
    - `<leader>-`: Number တွေကို လျှော့ပါ။

* * *

# Visual Mode select & Copy/Replace

- Cursor start current here
- vw: select word
- vwy: select word copy
- Mode : Normal mode


  ---
### Enter right delimiter 

**yswi** keymaps
- yswi: ဆိုရင် cursor current ကနေ word တွေကို ထပ်ထည့်လို့ရသည်။ enter double ဆိုရင် insert mode

  ---

