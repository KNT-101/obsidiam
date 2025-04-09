
JavaScript မှာ variable names တွေကို ပေးတဲ့အခါမှာ အောက်ပါ convention တွေကို လိုက်နာသင့်ပါတယ်။

### 1. **Camel Case**
   - Variable name ကို စပေးတဲ့အခါမှာ စာလုံးအသေးနဲ့စပြီး၊ နောက်စာလုံးတွေကို စာလုံးကြီးနဲ့စပါတယ်။
   - Example:
     ```javascript
     let firstName = "John";
     let totalAmount = 1000;
     let isActive = true;
     ```

### 2. **Meaningful Names**
   - Variable name ကို သူ့ရဲ့ လုပ်ဆောင်ချက်နဲ့ ကိုက်ညီတဲ့ အဓိပ္ပာယ်ရှိတဲ့ နာမည်ပေးသင့်ပါတယ်။
   - Example:
     ```javascript
     let userAge = 25; // Good
     let a = 25; // Bad (ဘာကိုဆိုလိုတာလဲဆိုတာ မသိရဘူး)
     ```

### 3. **No Reserved Keywords**
   - JavaScript မှာ သတ်မှတ်ထားတဲ့ reserved keywords တွေကို variable name အဖြစ် မသုံးသင့်ပါဘူး။
   - Example:
     ```javascript
     let let = 10; // Bad (let က reserved keyword ဖြစ်နေလို့)
     let function = "test"; // Bad
     ```

### 4. **Case Sensitive**
   - JavaScript က case sensitive ဖြစ်တာကြောင့် `firstName` နဲ့ `FirstName` ကို မတူညီတဲ့ variable အဖြစ် သတ်မှတ်ပါတယ်။
   - Example:
     ```javascript
     let firstName = "John";
     let FirstName = "Doe"; // ဒါက firstName နဲ့ မတူဘူး
     ```

### 5. **No Special Characters**
   - Variable name မှာ special characters (e.g., @, #, $, %) တွေ မပါသင့်ပါဘူး။ underscore (_) နဲ့ dollar sign ($) ကိုတော့ သုံးလို့ရပါတယ်။
   - Example:
     ```javascript
     let user_name = "John"; // Good
     let $amount = 100; // Good
     let user@name = "John"; // Bad
     ```

### 6. **Numbers in Names**
   - Variable name မှာ နံပါတ်တွေ ပါနိုင်ပေမယ့်၊ နံပါတ်နဲ့ စလို့မရပါဘူး။
   - Example:
     ```javascript
     let user1 = "Alice"; // Good
     let 1user = "Bob"; // Bad
     ```

### 7. **Constants**
   - Constant variable တွေကို သတ်မှတ်တဲ့အခါမှာ uppercase နဲ့သတ်မှတ်ပြီး၊ underscore နဲ့စာလုံးတွေကို ခွဲပါတယ်။
   - Example:
     ```javascript
     const PI = 3.14159;
     const MAX_USERS = 100;
     ```

### 8. **Avoid Single Letter Names**
   - Single letter variable names တွေကို ရှောင်သင့်ပါတယ်။ ဒါပေမယ့် loop တွေမှာတော့ သုံးလို့ရပါတယ်။
   - Example:
     ```javascript
     for (let i = 0; i < 10; i++) {
         console.log(i); // Good (loop မှာ i ကိုသုံးတာ common ဖြစ်တယ်)
     }

     let x = 5; // Bad (ဘာကိုဆိုလိုတာလဲဆိုတာ မသိရဘူး)
     ```

### 9. **Use Descriptive Names for Booleans**
   - Boolean variable တွေကို သတ်မှတ်တဲ့အခါမှာ `is`, `has`, `can`, `should` စတဲ့ prefix တွေနဲ့စပြီး သတ်မှတ်သင့်ပါတယ်။
   - Example:
     ```javascript
     let isLoggedIn = true;
     let hasPermission = false;
     let canEdit = true;
     ```

### 10. **Avoid Abbreviations**
   - Variable name တွေကို အတိုကောက်မသုံးဘဲ၊ ပြည့်ပြည့်စုံစုံ ရေးသင့်ပါတယ်။
   - Example:
     ```javascript
     let userAddress = "123 Main St"; // Good
     let addr = "123 Main St"; // Bad
     ```

### Summary
- **Camel Case** ကို အသုံးပြုပါ။
- **Meaningful** ဖြစ်တဲ့ variable names တွေကို ရွေးချယ်ပါ။
- **Reserved keywords** တွေကို ရှောင်ပါ။
- **Case Sensitive** ကို သတိထားပါ။
- **Constants** တွေကို uppercase နဲ့သတ်မှတ်ပါ။

ဒီ convention တွေကို လိုက်နာခြင်းအားဖြင့် code တွေကို ပိုမိုဖတ်ရလွယ်ကူစေပြီး၊ maintain လုပ်ရလွယ်ကူစေပါတယ်။