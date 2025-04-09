
### **Todo-comments.nvim Plugin အသုံးပြုပုံနှင့် Keybindings အသုံးချနည်း**  
ဒီ Note သည် `folke/todo-comments.nvim` ကို အဆင်ပြေပြေ အသုံးပြုဖို့အတွက် တိတိကျကျ ဖော်ပြထားပါသည်။ 

---

#### **1. Plugin Installation**  
Plugin ကို `lazy.nvim` သို့မဟုတ် `packer.nvim` သုံးပြီး ထည့်သွင်းပါ။  
```lua
return {
  "folke/todo-comments.nvim",
  event = { "BufReadPre", "BufNewFile" },
  dependencies = { "nvim-lua/plenary.nvim" },
  config = function()
    require("todo-comments").setup()
  end,
}
```

---

#### **2. အသုံးပြု Keybindings**
| Keybinding | Function                         | အသုံးပြုနည်း                                 |
|------------|----------------------------------|---------------------------------------------|
| `]t`       | Jump to **Next** TODO Comment    | TODO Comment တစ်ခုမှ နောက်တစ်ခုသို့ သွားရန် |
| `[t`       | Jump to **Previous** TODO Comment | TODO Comment တစ်ခုမှ ယခင်တစ်ခုသို့ သွားရန် |
| `:TodoTelescope` | Search TODO Comments with Telescope | Telescope မှာ TODO Comments ကိုရှာဖွေမည် |
| `:TodoQuickFix`  | Show TODOs in QuickFix List       | QuickFix List ထဲမှာ TODO တွေကို ပြမည်         |
| `:TodoTrouble`   | Show TODOs in Trouble.nvim        | Trouble.nvim မှာ TODO တွေကို ပြမည်            |

---

#### **3. TODO Comments Usage**
သင့် Project တွင် နေရာတိုင်းမှာ `TODO` သို့မဟုတ် အခြား Keywords တွေကို ရေးသားပြီး အသုံးပြုနိုင်သည်။  

**အသုံးပြုနိုင်သော Keywords**  

| Keyword | အဓိပ္ပာယ်                      | ဥပမာ                                       |
|---------|----------------------------------|-------------------------------------------|
| `TODO`  | To-Do Task ရေးထားခြင်း            | `-- TODO: Implement authentication`      |
| `FIX`   | Error တစ်ခုကို ပြန်လည်ပြင်ရန်       | `-- FIX: Resolve login issue`            |
| `BUG`   | Bug တစ်ခုကို ဖော်ပြခြင်း            | `-- BUG: Incorrect output on edge cases` |
| `HACK`  | Temporary fix ကို ရေးသားခြင်း       | `-- HACK: Dirty fix for compatibility`   |
| `PERF`  | Performance ကို တိုးတက်စေရန်       | `-- PERF: Optimize loop structure`       |
| `NOTE`  | သတိပေးမှုများ                     | `-- NOTE: Refactor this function later`  |
| `WARN`  | Warning message ရေးသားခြင်း        | `-- WARN: Avoid using global variables`  |

---

#### **4. Highlight Configuration**
TODO Comments တွေကို Highlight လုပ်ရန် Plugin မှ Default Settings သည်အောက်ပါအတိုင်း ဖြစ်သည်။  
```lua
require("todo-comments").setup {
  highlight = {
    keyword = "wide",  -- Highlight the entire keyword
    before = "",       -- No highlight before the keyword
    after = "fg",      -- Highlight after the keyword (foreground)
  },
  keywords = {
    TODO = { icon = " ", color = "info" },
    FIX  = { icon = " ", color = "error" },
    BUG  = { icon = " ", color = "error" },
    WARN = { icon = " ", color = "warning" },
    NOTE = { icon = " ", color = "hint" },
  },
}
```

---

#### **5. အသုံးပြုပုံ လက်တွေ့ဥပမာ**  
**Source Code Example**  
```lua
-- TODO: Refactor the authentication module
-- HACK: Added a quick workaround for the token validation
-- BUG: Edge cases fail when input exceeds the buffer size
-- PERF: Optimize the loop to reduce runtime complexity
-- NOTE: Double-check integration with the payment gateway
```

**Keybinding အလိုက် အသုံးပြုခြင်း**  
1. **TODO Comment Search:**  
   - `:TodoTelescope` ကို Command Line မှာရိုက်ပါ။
   - Telescope Interface မှာ TODO Comments တွေကို ပြပါမည်။

2. **Jump Between TODOs:**  
   - `[t` နှိပ်ပြီး ယခင် TODO Comment သို့သွားပါ။
   - `]t` နှိပ်ပြီး နောက်တစ်ခုသို့ သွားပါ။

---

#### **6. အသုံးပြုသော နေရာများ**
- Development နှင့် Debugging အတွက် အကောင်းဆုံး သုံးနိုင်သည်။
- TODO Tasks ကို တိတိကျကျ စီမံရန် အသုံးပြုနိုင်သည်။

---

```bash
-- Original code format 

return {
  "folke/todo-comments.nvim",
  event = { "BufReadPre", "BufNewFile" },
  dependencies = { "nvim-lua/plenary.nvim" },
  config = function()
    local todo_comments = require("todo-comments")

    -- set keymaps
    local keymap = vim.keymap -- for conciseness

    keymap.set("n", "]t", function()
      todo_comments.jump_next()
    end, { desc = "Next todo comment" })

    keymap.set("n", "[t", function()
      todo_comments.jump_prev()
    end, { desc = "Previous todo comment" })

    todo_comments.setup()
  end,
}

```


---
