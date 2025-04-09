
ဒီ Lua configuration ဖိုင်မှာ `gbprod/substitute.nvim` plugin ကို အသုံးပြုပြီး Vim keymap တွေကို သတ်မှတ်ထားပါတယ်။ ကိုယ့်ရဲ့ စာသားတွေကို **တည်ဆဲနေရာမှာပဲ အစားထိုး (substitute)** ပြုလုပ်ဖို့ အသုံးပြုတဲ့ plugin တစ်ခုဖြစ်ပါတယ်။

### အဓိပ္ပါယ်များ

```lua
keymap.set("mode", "key", function, { desc = "Description" })
```

- **mode**: Keybinding အသုံးပြုမယ့် mode (e.g., `n` = normal mode, `x` = visual mode)
- **key**: Bind လုပ်မယ့် key
- **function**: Plugin ရဲ့ လုပ်ဆောင်ချက် function
- **desc**: Keybinding ရဲ့ ဖော်ပြချက်

### သတ်မှတ်ထားသော Keybindings

#### 1\. **Normal Mode**

- **`s`**:
    
    - လိုရာ motion (e.g., word, paragraph) နဲ့ အစားထိုးဖို့ သုံးမယ့် command ပါ။
    - Example: `saw` => တစ်နှစ်လုံးကို အစားထိုးမည်။
- **`ss`**:
    
    - လိုက်တန်းတစ်လုံးလုံးကို အစားထိုးမယ်။
    - Example: `ss` => လက်ရှိ cursor ရှိတဲ့ line ကို အစားထိုးမည်။
- **`S`**:
    
    - လက်ရှိ cursor ရဲ့နေရာကနေ line အဆုံးထိအစားထိုးမယ်။
    - Example: `S` => လက်ရှိနေရာကနေ line အဆုံးထိ စာသားပြောင်းမယ်။

#### 2\. **Visual Mode**

- **`s`**:
    - Visual mode မှာ ရွေးထားတဲ့ selection ကို အစားထိုးမယ်။
    - Example: Visual mode မှာ စာသားရွေးပြီး `s` ကိုနှိပ်ပါ။

### အဓိက လိုအပ်ချက်

- **`substitute.operator`**: Motion နဲ့ အလုပ်လုပ်တယ်။
- **`substitute.line`**: တစ်လိုင်းလုံးကိုအစားထိုးတယ်။
- **`substitute.eol`**: Cursor နေရာကနေ လိုင်းအဆုံးထိ အစားထိုးတယ်။
- **`substitute.visual`**: Visual mode ရဲ့ selection နဲ့ အစားထိုးတယ်။

#### သုံးတဲ့အခါ

- **Motion-based**: `s` နဲ့ အစားထိုးဖို့အချိန် Motion Command တစ်ခုထည့်ပေးရတယ်။
- **Line-based**: `ss` နဲ့ အစားထိုးလို့ရတယ်။
- **EOL-based**: `S` နဲ့ Cursor မှာနေရာကနေ တန်းလုံးအစားထိုးလို့ရတယ်။
- **Visual-based**: Visual mode မှာ စာသားရွေးပြီး `s` ကိုသုံးပါ။

ဒီ plugin က တစ်ခုတည်းသော command နဲ့ စာသားတွေကိုမြန်မြန်အစားထိုးဖို့ အထောက်အကူပြုပါတယ်။ 