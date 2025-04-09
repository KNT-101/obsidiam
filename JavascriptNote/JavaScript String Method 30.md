
## 1️⃣ `length`  
String တစ်ခုမှာ ဘယ်နှစ်လုံးရှိတယ်ဆိုတာတွက်ပေးတဲ့ method  
```js
let text = "Hello, Kyaw!";
console.log(text.length); // Output: 13
```

---

## 2️⃣ `toUpperCase()`  
စာလုံးအားလုံးကို **uppercase** ပြောင်းမယ်  
```js
let text = "hello";
console.log(text.toUpperCase()); // Output: "HELLO"
```

---

## 3️⃣ `toLowerCase()`  
စာလုံးအားလုံးကို **lowercase** ပြောင်းမယ်  
```js
let text = "HELLO";
console.log(text.toLowerCase()); // Output: "hello"
```

---

## 4️⃣ `charAt(index)`  
တစ်လုံးချင်းစီကို index နဲ့ယူနိုင်မယ်  
```js
let text = "JavaScript";
console.log(text.charAt(4)); // Output: "S"
```

---

## 5️⃣ `indexOf(substring)`  
String ထဲမှာ substring **ရှိတဲ့ index** ကို return ပြန်မယ် (မရှိရင် `-1`)  
```js
let text = "Hello, world!";
console.log(text.indexOf("world")); // Output: 7
console.log(text.indexOf("Kyaw")); // Output: -1
```

---

## 6️⃣ `lastIndexOf(substring)`  
String ထဲမှာ **နောက်ဆုံး lần နေရာ** ကို return ပြန်မယ်  
```js
let text = "Hello, world! Hello!";
console.log(text.lastIndexOf("Hello")); // Output: 14
```

---

## 7️⃣ `slice(start, end)`  
String တစ်ခုမှ **တစ်ပိုင်းကိုဖြတ်ယူ** နိုင်မယ်  
```js
let text = "JavaScript";
console.log(text.slice(0, 4)); // Output: "Java"
console.log(text.slice(4));    // Output: "Script"
```

---

## 8️⃣ `substring(start, end)`  
**slice() နဲ့ဆင်တူပေမယ့် negative index မရ**  
```js
let text = "Hello, world!";
console.log(text.substring(7, 12)); // Output: "world"
```

---

## 9️⃣ `replace(searchValue, newValue)`  
String တစ်ခုထဲက **substring တစ်ခုကို အစားထိုး**  
```js
let text = "I love Python!";
console.log(text.replace("Python", "JavaScript")); // Output: "I love JavaScript!"
```
**📌 Note**: `replace()` က **ပထမ match တစ်ခုကိုပဲ** အစားထိုးမယ်။

---

## 🔟 `replaceAll(searchValue, newValue)`  
**String ထဲကတူညီတဲ့ substring တွေအားလုံးကို အစားထိုးမယ်**  
```js
let text = "I love Python! Python is great!";
console.log(text.replaceAll("Python", "JavaScript")); 
// Output: "I love JavaScript! JavaScript is great!"
```

---

## 1️⃣1️⃣ `trim()`  
String ရဲ့ **အစ & အနောက် space** တွေဖြုတ်လိုက်မယ်  
```js
let text = "   Hello, world!   ";
console.log(text.trim()); // Output: "Hello, world!"
```

---

## 1️⃣2️⃣ `split(separator)`  
String ကို array **ထဲကို ဖြတ်ထည့်မယ်**  
```js
let text = "apple,banana,orange";
console.log(text.split(",")); 
// Output: ["apple", "banana", "orange"]
```

---

## 1️⃣3️⃣ `startsWith(substring)`  
String ရဲ့ **အစမှာ substring ပါလား?**  
```js
let text = "Hello, Kyaw!";
console.log(text.startsWith("Hello")); // Output: true
console.log(text.startsWith("Kyaw"));  // Output: false
```

---

## 1️⃣4️⃣ `endsWith(substring)`  
String ရဲ့ **အဆုံးမှာ substring ပါလား?**  
```js
let text = "Hello, Kyaw!";
console.log(text.endsWith("Kyaw!")); // Output: true
console.log(text.endsWith("Hello"));  // Output: false
```

---

## 1️⃣5️⃣ `includes(substring)`  
String ထဲမှာ substring **ပါလား?**  
```js
let text = "I love JavaScript!";
console.log(text.includes("JavaScript")); // Output: true
console.log(text.includes("Python"));     // Output: false
```



### **These are the most useful JavaScript string methods**  


---

 **JavaScript String Methods (30 Methods) Table**  

| #  | Method | Description | Example | Output |
|----|------------|----------------------------------------|-----------------------------|-----------------|
| 1  | `length` | String length ကို return ပြန်မယ် | `"Hello".length` | `5` |
| 2  | `toUpperCase()` | Uppercase ပြောင်း | `"hello".toUpperCase()` | `"HELLO"` |
| 3  | `toLowerCase()` | Lowercase ပြောင်း | `"HELLO".toLowerCase()` | `"hello"` |
| 4  | `charAt(index)` | Index မှ character return | `"JavaScript".charAt(4)` | `"S"` |
| 5  | `indexOf(substring)` | First occurrence index return | `"Hello".indexOf("l")` | `2` |
| 6  | `lastIndexOf(substring)` | Last occurrence index return | `"Hello".lastIndexOf("l")` | `3` |
| 7  | `slice(start, end)` | String တစ်ခုပြိုခြင်း | `"JavaScript".slice(0, 4)` | `"Java"` |
| 8  | `substring(start, end)` | Slice လိုပေမယ့် negative index မရ | `"Hello".substring(1, 4)` | `"ell"` |
| 9  | `replace(search, newValue)` | First match ကို replace | `"I like JS".replace("JS", "Python")` | `"I like Python"` |
| 10 | `replaceAll(search, newValue)` | All matches ကို replace | `"JS JS".replaceAll("JS", "Python")` | `"Python Python"` |
| 11 | `trim()` | Spaces တွေဖြုတ် | `"  Hello  ".trim()` | `"Hello"` |
| 12 | `trimStart()` | Start space only ဖြုတ် | `"  Hello  ".trimStart()` | `"Hello  "` |
| 13 | `trimEnd()` | End space only ဖြုတ် | `"  Hello  ".trimEnd()` | `"  Hello"` |
| 14 | `split(separator)` | Array ကို ပြောင်း | `"a,b,c".split(",")` | `["a", "b", "c"]` |
| 15 | `startsWith(substring)` | Start match ရှိ/မရှိ | `"Hello".startsWith("He")` | `true` |
| 16 | `endsWith(substring)` | End match ရှိ/မရှိ | `"Hello".endsWith("lo")` | `true` |
| 17 | `includes(substring)` | String ထဲမှာ ပါ/မပါ | `"Hello".includes("ll")` | `true` |
| 18 | `repeat(n)` | String ကို `n` ချိန်ထပ်မယ် | `"Hi ".repeat(3)` | `"Hi Hi Hi "` |
| 19 | `padStart(length, pad)` | String ရဲ့ **အစမှာ padding** | `"5".padStart(3, "0")` | `"005"` |
| 20 | `padEnd(length, pad)` | String ရဲ့ **အဆုံးမှာ padding** | `"5".padEnd(3, "0")` | `"500"` |
| 21 | `concat(str1, str2)` | Strings တွေချိတ် | `"Hello".concat(" World")` | `"Hello World"` |
| 22 | `match(regex)` | Regex match တွေကို array ပြန်မယ် | `"abc".match(/[a-z]/g)` | `["a", "b", "c"]` |
| 23 | `matchAll(regex)` | All matches ကို iterator ပြန်မယ် | `Array.from("abc".matchAll(/a/g))` | `[["a"]]` |
| 24 | `search(regex)` | First match index return | `"Hello".search(/l/)` | `2` |
| 25 | `localeCompare(str)` | Sorting အတွက် Compare | `"a".localeCompare("b")` | `-1` |
| 26 | `toLocaleUpperCase()` | Locale-based Uppercase | `"i".toLocaleUpperCase("tr")` | `"İ"` |
| 27 | `toLocaleLowerCase()` | Locale-based Lowercase | `"İ".toLocaleLowerCase("tr")` | `"i"` |
| 28 | `codePointAt(index)` | Unicode point return | `"A".codePointAt(0)` | `65` |
| 29 | `fromCharCode(code)` | Unicode ကနေ String ပြောင်း | `String.fromCharCode(65)` | `"A"` |
| 30 | `normalize(form)` | Unicode Normalization | `"é".normalize("NFD")` | `"é"` |

📌 **မှတ်ချက်**  
**String methods တွေက အများကြီးရှိပေမယ့် ယင်း ၃၀ ခုက အထူးအသုံးဝင်တာတွေပါ။**  

---

