`ysiw` (surround.vim လို text object ကို surround လုပ်တဲ့ keymap) နဲ့ `ss` (အခြား keymap) တွေကို သင့်ရဲ့ Neovim config ထဲမှာ ထည့်သွင်းနိုင်ပါတယ်။ ဒီ keymaps တွေကို ထည့်သွင်းဖို့ `nvim-surround` plugin ကို အသုံးပြုပါမယ်။

* * *

## **`nvim-surround` Plugin** 

### **1\. `nvim-surround` Plugin ကို ထည့်ပါ**:

`lua/josean/plugins/init.lua` ဖိုင်ထဲမှာ `nvim-surround` plugin ကို  ထည့်သွင်းပါ။

```lua
return {
  { import = "josean.plugins.toggleterm" }, -- Add this line to load toggleterm
  { import = "josean.plugins.colorscheme" },
  { import = "josean.plugins.telescope" },
  { import = "josean.plugins.treesitter" },
  { import = "josean.plugins.lsp" },
  { import = "josean.plugins.linting" },
  { import = "josean.plugins.formatting" },
  { import = "josean.plugins.autopairs" },
  { import = "josean.plugins.comment" },
  { import = "josean.plugins.gitsigns" },
  { import = "josean.plugins.nvim-tree" },
  { import = "josean.plugins.lualine" },
  { import = "josean.plugins.todo-comments" },
  { import = "josean.plugins.trouble" },
  { import = "josean.plugins.which-key" },
  { import = "josean.plugins.surround" }, -- Add this line to load nvim-surround
}
```

* * *

### **2\. `surround.lua` ဖိုင်ကို ဖန်တီးပါ**:

`lua/josean/plugins/surround.lua` ဖိုင်ကို ဖန်တီးပါ။

```lua
-- lua/josean/plugins/surround.lua
return {
  "kylechui/nvim-surround",
  version = "*", -- Use for stability; omit to use `main` branch for the latest features
  config = function()
    require("nvim-surround").setup({
      -- Configuration options (optional)
    })
  end,
}
```

* * *

### **3\. Keymaps များ**:

`nvim-surround` plugin ကို ထည့်သွင်းပြီးရင် အောက်ပါ keymaps တွေကို အလိုအလျောက် ရရှိပါလိမ့်မယ်။

#### **Default Keymaps**:

- **`ysiw`**:
    
    - **Mode**: Normal mode
    - **Action**: Surround a word with a character (e.g., `ysiw"` to surround a word with double quotes).
    - **Description**: `ysiw` ကို သုံးပြီး word တစ်ခုကို surround လုပ်နိုင်ပါတယ်။
- **`yss`**:
    
    - **Mode**: Normal mode
    - **Action**: Surround the entire line with a character (e.g., `yss"` to surround the line with double quotes).
    - **Description**: `yss` ကို သုံးပြီး line တစ်ခုလုံးကို surround လုပ်နိုင်ပါတယ်။
- **`ds`**:
    
    - **Mode**: Normal mode
    - **Action**: Delete surrounding characters (e.g., `ds"` to delete surrounding double quotes).
    - **Description**: `ds` ကို သုံးပြီး surround characters တွေကို ဖျက်နိုင်ပါတယ်။
- **`cs`**:
    
    - **Mode**: Normal mode
    - **Action**: Change surrounding characters (e.g., `cs"'` to change double quotes to single quotes).
    - **Description**: `cs` ကို သုံးပြီး surround characters တွေကို ပြောင်းနိုင်ပါတယ်။

* * *

### **4\. Custom Keymaps**:

- custom keymaps တွေကို ထပ်မံထည့်သွင်းလို့ရပါတယ်။

```lua
-- lua/josean/plugins/surround.lua
return {
  "kylechui/nvim-surround",
  version = "*", -- Use for stability; omit to use `main` branch for the latest features
  config = function()
    require("nvim-surround").setup({
      -- Configuration options (optional)
    })

    -- Custom keymaps
    local keymap = vim.keymap
    keymap.set("n", "<leader>sw", "ysiw", { desc = "Surround word" }) -- Surround a word
    keymap.set("n", "<leader>sl", "yss", { desc = "Surround line" }) -- Surround a line
    keymap.set("n", "<leader>sd", "ds", { desc = "Delete surrounding" }) -- Delete surrounding
    keymap.set("n", "<leader>sc", "cs", { desc = "Change surrounding" }) -- Change surrounding
  end,
}
```

* * *

### **အသုံးပြုနည်း**:

1.  **Surround a Word**:
    
    - `ysiw"`: Word တစ်ခုကို double quotes နဲ့ surround လုပ်ပါ။
    - `ysiw(`: Word တစ်ခုကို parentheses နဲ့ surround လုပ်ပါ။
2.  **Surround a Line**:
    
    - `yss"`: Line တစ်ခုလုံးကို double quotes နဲ့ surround လုပ်ပါ။
    - `yss{`: Line တစ်ခုလုံးကို curly braces နဲ့ surround လုပ်ပါ။
3.  **Delete Surrounding**:
    
    - `ds"`: Double quotes တွေကို ဖျက်ပါ။
    - `ds(`: Parentheses တွေကို ဖျက်ပါ။
4.  **Change Surrounding**:
    
    - `cs"'`: Double quotes ကို single quotes အဖြစ် ပြောင်းပါ။
    - `cs({`: Parentheses ကို curly braces အဖြစ် ပြောင်းပါ။

* * *

### **မှတ်ချက်**:

- `nvim-surround` plugin ကို မှန်ကန်စွာ setup လုပ်ပြီး `ysiw`, `ss`, `ds`, `cs` တို့ကို အဆင်ပြေပြေသုံးလို့ရပါပီ။