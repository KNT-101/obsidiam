
## **JavaScript String Methods Overview**

| **Method**          | **Description**                                                                 | **Example**                                                                                     |
|---------------------|---------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|
| `charAt(index)`     | ပေးထားတဲ့ Index မှာရှိတဲ့ Character ကို ပြန်ပေးတယ်။                           | `"Hello".charAt(1);` → Output: `'e'`                                                            |
| `charCodeAt(index)` | ပေးထားတဲ့ Index မှာရှိတဲ့ Character ရဲ့ Unicode Value ကို ပြန်ပေးတယ်။        | `"Hello".charCodeAt(0);` → Output: `72`                                                         |
| `concat(str1, str2)`| String တွေကို ပေါင်းစပ်ပေးတယ်။                                             | `"Hello ".concat("World!");` → Output: `'Hello World!'`                                         |
| `endsWith(searchStr)`| String က ပေးထားတဲ့ Substring နဲ့ ဆုံးသလား စစ်ပေးတယ်။                   | `"Hello, World!".endsWith("World!");` → Output: `true`                                          |
| `includes(searchStr)`| String ထဲမှာ ပေးထားတဲ့ Substring ပါလား စစ်ပေးတယ်။                       | `"Hello, World!".includes("World");` → Output: `true`                                           |
| `indexOf(searchStr)`| ပေးထားတဲ့ Substring ရဲ့ ပထမဆုံး Index ကို ပြန်ပေးတယ် (မတွေ့ရင် -1)။       | `"Hello, World!".indexOf("World");` → Output: `7`                                               |
| `lastIndexOf(searchStr)`| ပေးထားတဲ့ Substring ရဲ့ နောက်ဆုံး Index ကို ပြန်ပေးတယ် (မတွေ့ရင် -1)။| `"Hello, World, Hello!".lastIndexOf("Hello");` → Output: `13`                                   |
| `match(regexp)`     | Regular Expression ကို သုံးပြီး String ထဲမှာ Match လုပ်တဲ့ အချက်တွေ ပြန်ပေးတယ်။ | `"Hello123".match(/\d+/);` → Output: `['123']`                                                 |
| `repeat(count)`     | String ကို ပေးထားတဲ့ Count အရ ထပ်ထည့်ပေးတယ်။                              | `"Ha".repeat(3);` → Output: `'HaHaHa'`                                                          |
| `replace(search, replaceStr)`| String ထဲက ပေးထားတဲ့ Substring ကို အစားထိုးပေးတယ်။           | `"Hello, World!".replace("World", "JavaScript");` → Output: `'Hello, JavaScript!'`              |
| `replaceAll(search, replaceStr)`| String ထဲက ပေးထားတဲ့ Substring အားလုံးကို အစားထိုးပေးတယ်။    | `"Hello, World! World!".replaceAll("World", "JS");` → Output: `'Hello, JS! JS!'`                |
| `search(regexp)`    | Regular Expression ကို သုံးပြီး String ထဲမှာ Match လုပ်တဲ့ Index ကို ပြန်ပေးတယ်။ | `"Hello123".search(/\d/);` → Output: `5`                                                       |
| `slice(start, end)` | String ထဲက ပေးထားတဲ့ Range အတွင်းက Substring ကို ပြန်ပေးတယ်။            | `"Hello, World!".slice(0, 5);` → Output: `'Hello'`                                              |
| `split(separator)`  | String ကို Separator အတိုင်း ခွဲပြီး Array အဖြစ် ပြန်ပေးတယ်။            | `"apple,banana,cherry".split(",");` → Output: `['apple', 'banana', 'cherry']`                   |
| `startsWith(searchStr)`| String က ပေးထားတဲ့ Substring နဲ့ စတာလား စစ်ပေးတယ်။                 | `"Hello, World!".startsWith("Hello");` → Output: `true`                                         |
| `substring(start, end)`| String ထဲက ပေးထားတဲ့ Range အတွင်းက Substring ကို ပြန်ပေးတယ်။      | `"Hello, World!".substring(0, 5);` → Output: `'Hello'`                                          |
| `toLowerCase()`     | String ကို အားလုံး Lowercase ပြောင်းပေးတယ်။                               | `"HELLO".toLowerCase();` → Output: `'hello'`                                                    |
| `toUpperCase()`     | String ကို အားလုံး Uppercase ပြောင်းပေးတယ်။                               | `"hello".toUpperCase();` → Output: `'HELLO'`                                                    |
| `trim()`            | String ရဲ့ အစ နဲ့ အဆုံးမှာ ပါတဲ့ Whitespace တွေကို ဖယ်ရှားပေးတယ်။         | `"   Hello, World!   ".trim();` → Output: `'Hello, World!'`                                     |
| `trimStart()`       | String ရဲ့ အစမှာ ပါတဲ့ Whitespace တွေကို ဖယ်ရှားပေးတယ်။                  | `"   Hello, World!".trimStart();` → Output: `'Hello, World!'`                                   |
| `trimEnd()`         | String ရဲ့ အဆုံးမှာ ပါတဲ့ Whitespace တွေကို ဖယ်ရှားပေးတယ်။             | `"Hello, World!   ".trimEnd();` → Output: `'Hello, World!'`                                     |
| `padStart(targetLength, padString)`| String ကို ဘယ်ဘက်မှာ Pad String ဖြည့်ပေးတယ်။               | `"5".padStart(4, "0");` → Output: `'0005'`                                                     |
| `padEnd(targetLength, padString)`| String ကို ညာဘက်မှာ Pad String ဖြည့်ပေးတယ်။                    | `"5".padEnd(4, "0");` → Output: `'5000'`                                                       |
| `localeCompare(str)`| String နှစ်ခုကို နှိုင်းယှဉ်ပြီး ပြန်ပေးတယ် (Alphabetical Order)။       | `"apple".localeCompare("banana");` → Output: `-1` (apple comes before banana)                   |
| `toString()`        | String ကို ပြန်ပေးတယ်။ (Number တွေကို String အဖြစ် ပြောင်းဖို့ သုံးတယ်)   | `(123).toString();` → Output: `'123'`                                                          |
| `valueOf()`         | String Object ရဲ့ Primitive Value ကို ပြန်ပေးတယ်။                          | `new String("Hello").valueOf();` → Output: `'Hello'`                                            |

---

### **Advanced Examples**

#### **1. Regular Expression with `match()`**
```javascript
let text = "The rain in SPAIN stays mainly in the plain";
let matches = text.match(/ain/gi); // 'g' for global, 'i' for case-insensitive
console.log(matches); // Output: ['ain', 'AIN', 'ain', 'ain']
```

#### **2. Using `split()` and `join()` Together**
```javascript
let sentence = "JavaScript is fun!";
let words = sentence.split(" "); // Split by space
let reversed = words.reverse().join(" "); // Reverse and join back
console.log(reversed); // Output: 'fun! is JavaScript'
```

#### **3. Padding Strings**
```javascript
let num = "7";
let paddedNum = num.padStart(4, "0"); // Pad with zeros to make it 4 characters long
console.log(paddedNum); // Output: '0007'

let paddedNumEnd = num.padEnd(4, "*"); // Pad with asterisks at the end
console.log(paddedNumEnd); // Output: '7***'
```

#### **4. Replacing All Occurrences with `replaceAll()`**
```javascript
let text = "I love cats. Cats are cute.";
let replacedText = text.replaceAll("Cats", "Dogs");
console.log(replacedText); // Output: 'I love cats. Dogs are cute.'
```

#### **5. Trimming Strings**
```javascript
let text = "   Hello, World!   ";
console.log(text.trim()); // Output: 'Hello, World!'
console.log(text.trimStart()); // Output: 'Hello, World!   '
console.log(text.trimEnd()); // Output: '   Hello, World!'
```

#### **6. Combining Multiple Methods**
```javascript
let text = "   hello world   ";
let result = text.trim().toUpperCase().split(" ").join("-");
console.log(result); // Output: 'HELLO-WORLD'
```

---

