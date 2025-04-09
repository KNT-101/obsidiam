
# Primitive Data Types


JavaScript ရဲ့ **Primitive Data Types** ဆိုတာက JavaScript မှာ အခြေခံအနေနဲ့ အသုံးပြုလေ့ရှိတဲ့ data types တွေဖြစ်ပါတယ်။ Primitive data types တွေဟာ immutable (ပြောင်းလဲလို့မရဘူး) ဖြစ်ပြီး၊ သူတို့ရဲ့ value တွေကို တိုက်ရိုက် သိမ်းဆည်းထားတာဖြစ်ပါတယ်။ JavaScript မှာ အဓိက primitive data types တွေက အောက်ပါအတိုင်း ရှိပါတယ်။

---

### 1. **String**
- **Definition**: စာသား (text) တွေကို ကိုယ်စားပြုတဲ့ data type ဖြစ်ပါတယ်။ String တွေကို single quotes (`'`), double quotes (`"`) သို့မဟုတ် backticks (\``) နဲ့ ဖော်ပြလေ့ရှိပါတယ်။
- **Example**:
  ```javascript
  let name = "John Doe"; // Double quotes
  let message = 'Hello, World!'; // Single quotes
  let template = `My name is ${name}`; // Template literals with backticks
  console.log(name); // Output: John Doe
  console.log(message); // Output: Hello, World!
  console.log(template); // Output: My name is John Doe
  ```

---

### 2. **Number**
- **Definition**: ဂဏန်းတွေ (integer နဲ့ floating-point numbers) ကို ကိုယ်စားပြုတဲ့ data type ဖြစ်ပါတယ်။ JavaScript မှာ number တွေဟာ 64-bit floating point format နဲ့ သိမ်းဆည်းထားပါတယ်။
- **Example**:
  ```javascript
  let age = 25; // Integer
  let price = 19.99; // Floating-point number
  let negative = -10; // Negative number
  console.log(age); // Output: 25
  console.log(price); // Output: 19.99
  console.log(negative); // Output: -10
  ```

---

### 3. **Boolean**
- **Definition**: အမှန် (true) နဲ့ မှား (false) တို့ကို ကိုယ်စားပြုတဲ့ data type ဖြစ်ပါတယ်။ Conditional statements တွေမှာ အသုံးပြုလေ့ရှိပါတယ်။
- **Example**:
  ```javascript
  let isLoggedIn = true;
  let isAdmin = false;
  console.log(isLoggedIn); // Output: true
  console.log(isAdmin); // Output: false
  ```

---

### 4. **Undefined**
- **Definition**: Variable တစ်ခုကို declare လုပ်ထားပေမယ့် value မထည့်ပေးရသေးဘူးဆိုရင် အလိုအလျောက် `undefined` ဖြစ်ပါတယ်။
- **Example**:
  ```javascript
  let username;
  console.log(username); // Output: undefined
  ```

---

### 5. **Null**
- **Definition**: Null ဆိုတာက "ဘာမှမရှိဘူး" လို့ ပြောတဲ့ value ဖြစ်ပါတယ်။ ဒါက developer က သဘောကျပြီး ထည့်ပေးတာဖြစ်ပါတယ်။
- **Example**:
  ```javascript
  let user = null;
  console.log(user); // Output: null
  ```

---

### 6. **Symbol (ES6 မှစပြီးပါဝင်)**
- **Definition**: Symbol ဆိုတာက unique ဖြစ်တဲ့ identifier တစ်ခုဖြစ်ပါတယ်။ Object ရဲ့ property keys အနေနဲ့ အသုံးပြုလေ့ရှိပါတယ်။
- **Example**:
  ```javascript
  let id = Symbol("id");
  let anotherId = Symbol("id");
  console.log(id === anotherId); // Output: false (Symbols are always unique)
  ```

---

### 7. **BigInt (ES2020 မှစပြီးပါဝင်)**
- **Definition**: BigInt ဆိုတာက အရမ်းကို ကြီးတဲ့ integer တွေကို ကိုယ်စားပြုဖို့အတွက် အသုံးပြုတဲ့ data type ဖြစ်ပါတယ်။ Number type က safe ဖြစ်တဲ့ maximum value ကို ကျော်လွန်တဲ့ ဂဏန်းတွေအတွက် အသုံးပြုပါတယ်။
- **Example**:
  ```javascript
  let bigNumber = 9007199254740991n; // Adding 'n' makes it a BigInt
  console.log(bigNumber); // Output: 9007199254740991n
  ```

---

### Summary Table of Primitive Data Types

| Data Type | Description                          | Example                  |
|-----------|--------------------------------------|--------------------------|
| String    | Text or characters                   | `"Hello"`, `'World'`     |
| Number    | Integers or floating-point numbers   | `42`, `3.14`             |
| Boolean   | True or False                        | `true`, `false`          |
| Undefined | Variable declared but not assigned   | `let x;`                 |
| Null      | Represents "nothing" or "empty"      | `null`                   |
| Symbol    | Unique and immutable identifier      | `Symbol("unique")`       |
| BigInt    | Large integers                       | `123456789012345678901n` |

---

### Key Points to Remember:
1. **Primitive data types** တွေဟာ immutable ဖြစ်တယ်။ ဆိုလိုတာက value တွေကို တိုက်ရိုက် ပြောင်းလဲလို့မရဘူး။
2. **Type Checking**: `typeof` operator ကို သုံးပြီး primitive data type ကို စစ်ဆေးနိုင်ပါတယ်။
   ```javascript
   console.log(typeof "Hello"); // Output: string
   console.log(typeof 42); // Output: number
   console.log(typeof true); // Output: boolean
   console.log(typeof undefined); // Output: undefined
   console.log(typeof null); // Output: object (This is a known bug in JavaScript)
   console.log(typeof Symbol("id")); // Output: symbol
   console.log(typeof 123456789012345678901n); // Output: bigint
   ```

---

# Reference data type 


JavaScript ရဲ့ **reference data types** ဆိုတာက value တစ်ခုကို memory ထဲမှာ reference (address) အနေနဲ့သိမ်းဆည်းပြီး၊ variable တစ်ခုက ဒီ reference ကို ညွှန်ပြတဲ့အတွက် ဖြစ်ပါတယ်။ Reference data types တွေဟာ primitive data types (number, string, boolean, etc.) တွေနဲ့ ကွာခြားတာက သူတို့ဟာ memory ထဲမှာ တည်ဆောက်ထားတဲ့ object တစ်ခုကို ညွှန်ပြတာဖြစ်ပြီး၊ ဒီ object ကို တစ်ခုထက်ပိုတဲ့ variables တွေက အတူတူ share လုပ်နိုင်ပါတယ်။

JavaScript မှာ reference data types အဓိက အမျိုးအစားတွေကတော့ **Object**, **Array**, နဲ့ **Function** တို့ဖြစ်ပါတယ်။ အခု အောက်မှာ ဒီ data types တွေကို အသေးစိတ် ရှင်းပြပါမယ်။

---

### 1. **Object**
Object ဆိုတာက key-value pairs တွေပါဝင်တဲ့ complex data structure တစ်ခုဖြစ်ပါတယ်။ Object တစ်ခုကို variable တစ်ခုမှာ assign လုပ်လိုက်ရင်၊ ဒီ variable က object ရဲ့ memory address ကို ညွှန်ပြပါမယ်။

#### Example:
```javascript
let person1 = { name: "John", age: 25 };
let person2 = person1; // person2 က person1 ရဲ့ reference ကို ရယူလိုက်တယ်

person2.age = 30; // person2 ကို ပြောင်းလိုက်တာနဲ့ person1 လည်း ပြောင်းသွားမယ်

console.log(person1); // Output: { name: "John", age: 30 }
console.log(person2); // Output: { name: "John", age: 30 }
```

**Explanation:**  
`person1` နဲ့ `person2` ဟာ အတူတူ object တစ်ခုကို reference လုပ်ထားတဲ့အတွက်၊ တစ်ခုကို ပြောင်းလိုက်ရင် နောက်တစ်ခုလည်း ပြောင်းသွားပါတယ်။

---

### 2. **Array**
Array ဆိုတာက ordered collection of values တွေဖြစ်ပြီး၊ JavaScript မှာ array တစ်ခုက object တစ်ခုအဖြစ်သို့ ပြောင်းလဲသုံးနိုင်ပါတယ်။ Array ကိုလည်း reference အနေနဲ့ သိမ်းဆည်းပါတယ်။

#### Example:
```javascript
let arr1 = [1, 2, 3];
let arr2 = arr1; // arr2 က arr1 ရဲ့ reference ကို ရယူလိုက်တယ်

arr2.push(4); // arr2 ကို ပြောင်းလိုက်တာနဲ့ arr1 လည်း ပြောင်းသွားမယ်

console.log(arr1); // Output: [1, 2, 3, 4]
console.log(arr2); // Output: [1, 2, 3, 4]
```

**Explanation:**  
`arr1` နဲ့ `arr2` ဟာ အတူတူ array တစ်ခုကို reference လုပ်ထားတဲ့အတွက်၊ တစ်ခုကို ပြောင်းလိုက်ရင် နောက်တစ်ခုလည်း ပြောင်းသွားပါတယ်။

---

### 3. **Function**
Function တစ်ခုကလည်း reference data type တစ်ခုဖြစ်ပြီး၊ function တစ်ခုကို variable တစ်ခုမှာ assign လုပ်လိုက်ရင် ဒီ variable က function ရဲ့ reference ကို ညွှန်ပြပါမယ်။

#### Example:
```javascript
function greet() {
    console.log("Hello!");
}

let sayHello = greet; // sayHello က greet function ရဲ့ reference ကို ရယူလိုက်တယ်

sayHello(); // Output: Hello!
greet();    // Output: Hello!
```

**Explanation:**  
`sayHello` နဲ့ `greet` ဟာ အတူတူ function တစ်ခုကို reference လုပ်ထားတဲ့အတွက်၊ တစ်ခုကို call လုပ်လိုက်ရင် နောက်တစ်ခုလည်း အလုပ်လုပ်ပါတယ်။

---

### 4. **Deep Copy vs Shallow Copy**
Reference data types တွေကို copy လုပ်တဲ့အခါမှာ shallow copy နဲ့ deep copy ဆိုပြီး ကွဲပြားတာကို သတိပြုဖို့လိုပါတယ်။

#### Shallow Copy
Shallow copy ဆိုတာက reference ကို မတူညီတဲ့ variable တစ်ခုကို assign လုပ်ပေမယ့်၊ nested objects တွေကိုတော့ မကောက်ထားပါဘူး။

```javascript
let obj1 = { a: 1, b: { c: 2 } };
let obj2 = { ...obj1 }; // Spread operator ကိုသုံးပြီး shallow copy လုပ်လိုက်တယ်

obj2.b.c = 3;

console.log(obj1); // Output: { a: 1, b: { c: 3 } }
console.log(obj2); // Output: { a: 1, b: { c: 3 } }
```

**Explanation:**  
`obj1` နဲ့ `obj2` ဟာ `b` property ရဲ့ nested object ကို တူညီတဲ့ reference ကို သုံးထားတဲ့အတွက်၊ `obj2` ကို ပြောင်းလိုက်တာနဲ့ `obj1` လည်း ပြောင်းသွားပါတယ်။

#### Deep Copy
Deep copy ဆိုတာက nested objects တွေအထိ အပြည့်အဝ ကောက်ယူပြီး အသစ်ဖန်တီးပေးတာဖြစ်ပါတယ်။

```javascript
let obj1 = { a: 1, b: { c: 2 } };
let obj2 = JSON.parse(JSON.stringify(obj1)); // Deep copy လုပ်လိုက်တယ်

obj2.b.c = 3;

console.log(obj1); // Output: { a: 1, b: { c: 2 } }
console.log(obj2); // Output: { a: 1, b: { c: 3 } }
```

**Explanation:**  
`obj2` ဟာ `obj1` ရဲ့ deep copy ဖြစ်တဲ့အတွက်၊ `obj2` ကို ပြောင်းလိုက်တာနဲ့ `obj1` က မပြောင်းပါဘူး။

---

### 5. **Pass by Reference**
JavaScript မှာ function တစ်ခုကို parameter အနေနဲ့ object တစ်ခုကို pass လုပ်လိုက်ရင်၊ ဒီ object ဟာ reference အနေနဲ့ pass လုပ်တာဖြစ်ပါတယ်။

#### Example:
```javascript
function updateAge(person) {
    person.age = 30;
}

let john = { name: "John", age: 25 };
updateAge(john);

console.log(john); // Output: { name: "John", age: 30 }
```

**Explanation:**  
`john` ဟာ reference အနေနဲ့ `updateAge` function ထဲကို pass လုပ်ထားတဲ့အတွက်၊ function ထဲမှာ `person.age` ကို ပြောင်းလိုက်တာနဲ့ `john` object ကလည်း ပြောင်းသွားပါတယ်။

---

### Reference Conclusion
JavaScript ရဲ့ reference data types တွေက memory ထဲမှာ reference (address) အနေနဲ့ သိမ်းဆည်းတာဖြစ်ပြီး၊ ဒီ reference ကို တစ်ခုထက်ပိုတဲ့ variables တွေက အတူတူ share လုပ်နိုင်ပါတယ်။ Reference data types တွေကို သုံးတဲ့အခါမှာ shallow copy နဲ့ deep copy တို့ရဲ့ ကွဲပြားချက်ကို သတိပြုဖို့ အရေးကြီးပါတယ်။

---

### Premitive Final Answer:
JavaScript ရဲ့ primitive data types တွေက **String**, **Number**, **Boolean**, **Undefined**, **Null**, **Symbol**, နဲ့ **BigInt** တို့ဖြစ်ပါတယ်။ သူတို့က immutable ဖြစ်ပြီး၊ အခြေခံ programming မှာ အရမ်းကို အရေးကြီးတဲ့အပိုင်းတွေဖြစ်ပါတယ်။