
# ${\color{red} Step \space By \space Step}$

## ${\color{blue}Virtual \space Environment \space setup \space Commands }$

```bash
python3 -m venv <usernamefile=env>
```


```bash
source <username=env>/bin/activate
```
 

```bash
deactivate = virtual environment ရပ်ခြင်း ။
```




---

*မိမိလိုအပ်သော Package or Package pip များကို installation လုပ်ပါ။ မိမိ sys မပျက်စီးအောင် virtual environment ဆောက်ပြီး package installation လုပ်ခြင်းသည် ပိုကောင်းပါသည်။*


---


Python Virtual Environment (venv) က Python project တစ်ခုချင်းစီအတွက် အထူးပြုစီမံထားတဲ့ environment ဖြစ်ပြီး Python packages တွေကို အခြား project တွေနဲ့ ခြားနားစွာသိမ်းဆည်းနိုင်ပါတယ်။  
အဓိက ရည်ရွယ်ချက်ကတော့ Project တစ်ခုချင်းစီမှာ အသုံးပြုမယ့် packages version တွေကို ချက်ချင်းလွယ်လွယ်ကူကူ ထိန်းချုပ်နိုင်ရန် ဖြစ်ပါတယ်။

---

###  Python Virtual Environment တည်ဆောက်ခြင်း နဲ့ အသုံးပြုခြင်း - Step by Step

#### **Step 1: Python Install ဖြစ်ကြောင်းစစ်ဆေးပါ**

Python version ကိုစစ်ဆေးဖို့ Terminal မှာ အောက်ပါ command ကိုရိုက်ပါ။

```bash
python3 --version
```

❗ အဆင်မပြေတာမျိုးဖြစ်ရင် Python ကို Install လုပ်ထားဖို့လိုပါတယ်။

---

#### **Step 2: Virtual Environment တည်ဆောက်ပါ**

Project folder ထဲသို့ ဝင်ပါ။

```bash
mkdir my_project
cd my_project
```

Virtual environment တည်ဆောက်ဖို့ အောက်ပါ command ကိုအသုံးပြုပါ။

```bash
python3 -m venv env
```

**သတိပြုရန်:**

- `venv` ကတော့ Python built-in module ဖြစ်ပါတယ်။
    
- `env` ဆိုတာက Virtual environment folder ရဲ့အမည်ပါ။
    
- အမည်ကို ကိုယ်ကြိုက်တဲ့အတိုင်းပြောင်းလဲနိုင်ပါတယ်။
    

---

#### **Step 3: Virtual Environment ကို စတင်အသုံးပြုပါ**

Virtual environment ကို activate လုပ်ပါ။

**Linux/MacOS:**

```bash
source env/bin/activate
```

**Windows:**

```bash
.\env\Scripts\activate
```

 Activate လုပ်ပြီးရင် Terminal အမည်ရှေ့မှာ `(env)` လို့ပေါ်လာပါလိမ့်မယ်။

---

#### **Step 4: Packages တပ်ပြီး အသုံးပြုပါ**

Virtual environment အတွင်းမှာ package တွေကို အောက်ပါအတိုင်း install လုပ်ပါ။

```bash
pip install requests
```

Package များကို စစ်ဆေးရန်

```bash
pip list
```

---

#### **Step 5: Virtual Environment မှထွက်ရန် (Deactivate)**

Virtual environment မှထွက်ရန်

```bash
deactivate
```

---

###  Virtual Environment ကိုဖျက်ရန်

Virtual environment ကိုဖျက်ဖို့ folder ကို လုံးဝဖျက်သိမ်းလိုက်ရင် ရပါပြီ။

```bash
rm -rf env
```

---

### Note

- Virtual environment သည် project တစ်ခုချင်းစီအတွက် အထူးပြု Python environment တည်ဆောက်ရန် အသုံးပြုသည်။
    
- Packages များကို တစ်ခုချင်းစီသိမ်းဆည်းပြီး Project တွေကြားမှာ version conflicts မဖြစ်အောင် ကာကွယ်နိုင်သည်။
    
- Activate လုပ်ပြီး Package များကို install လုပ်ပြီးရင် deactivate လုပ်၍ ထွက်နိုင်သည်။

---
# Requirements.txt အကြောင်း 

---

### **🔹 Requirements File (`requirements.txt`) ဘာလဲ?**

`requirements.txt` ဆိုတာက Python project တစ်ခုမှာ အသုံးပြုတဲ့ **package list** တွေကို သိမ်းဆည်းထားတဲ့ **text file** တစ်ခုပါ။  
ဒီ file ကြောင့် project ကို ပြန်တည်ဆောက်ရလွယ်ပြီး တခြားသူတွေလည်း အလွယ်တကူ install လုပ်နိုင်ပါတယ်။

---

### **Step 1: Project မှာ အသုံးပြုနေတဲ့ Packages တွေ Export လုပ်ခြင်း**

Project မှာ install လုပ်ထားတဲ့ **Python packages** တွေကို `requirements.txt` ထဲမှာ သိမ်းဖို့ အောက်ပါ command ကိုအသုံးပြုပါ။

```bash
pip freeze > requirements.txt
```

🔹 **ဘာဖြစ်လဲ?**  
ဒီ command ကိုသုံးလိုက်ရင် `requirements.txt` file ထဲမှာ project မှာ install ထားတဲ့ **package name နဲ့ version** တွေထည့်ပေးမှာပါ။  
ဥပမာ၊ `requirements.txt` ထဲမှာ အောက်လိုမျိုးထွက်လာနိုင်ပါတယ် ⬇️

```
Flask==2.0.3
requests==2.31.0
numpy==1.24.3
```

---

### **Step 2: Requirements File ကို အသုံးပြု၍ Dependencies Install လုပ်ခြင်း**

Project ကို တခြား device မှာ သို့မဟုတ် အသစ် setup လုပ်ချင်ရင် **dependencies** တွေကို install လုပ်ဖို့ အောက်ပါ command ကိုအသုံးပြုနိုင်ပါတယ်။

```bash
pip install -r requirements.txt
```

🔹 **ဘာဖြစ်မလဲ?**  
ဒီ command က `requirements.txt` ထဲမှာ **သိမ်းထားတဲ့ packages တွေကို အတိအကျ install** လုပ်ပေးမယ်။

---

### **Step 3: Custom Requirements File များ**

တခါတလဲ **Development** နဲ့ **Production** အတွက် အခြား requirements file တွေလည်း သီးခြားအသုံးပြုနိုင်ပါတယ်။  
ဥပမာ -

#### 🔸 **Development Requirements**

```bash
pip freeze > dev-requirements.txt
pip install -r dev-requirements.txt
```

#### 🔸 **Production Requirements**

```bash
pip freeze --exclude-editable > prod-requirements.txt
pip install -r prod-requirements.txt
```

---

### **Note**

✅ `pip freeze > requirements.txt` — အသုံးပြုနေတဲ့ packages တွေကို သိမ်းခြင်း  
✅ `pip install -r requirements.txt` — တခြားသူများ install လုပ်လွယ်အောင်  
✅ Development & Production အတွက် အထူးပြု requirements files ကို အသုံးပြုနိုင်မည်

---

### **🔹 `pip freeze` ဘာလုပ်လဲ?**

```bash
pip freeze
```

 **Current environment ထဲမှာ install လုပ်ထားတဲ့** **pip packages** တွေကို output ထုတ်ပေးတယ်။  
Example 

```
Flask==2.2.2
requests==2.31.0
numpy==1.24.3
```

---

### **🔹 `>>` Operator - Append Mode**

ဒါပဲ **Overwrite မလုပ်ဘဲ ပေါင်းထည့်ချင်ရင်** `>>` ကိုအသုံးပြုနိုင်တယ်။

```bash
pip freeze >> requirements.txt
```

✅ **Existing `requirements.txt` ထဲမှာ အသစ် install လုပ်ထားတဲ့ package တွေကို ပေါင်းထည့်မယ်။**  
✅ **Overwrite မလုပ်ဘဲ ရှိတာထဲ ပေါင်းထည့်တာ။**

---

### **ထပ်မံ သိထားသင့်တဲ့ Command များ**

**1️⃣ Package ကို version မပါဘဲ export လုပ်ချင်ရင်:**

```bash
pip freeze | cut -d "=" -f 1 > requirements.txt
```

ဒီလိုလုပ်ရင် `requests==2.31.0` ဆိုတာ **`requests`** ပဲဖြစ်သွားမယ်။

**2️⃣ တချို့ packages တွေမထည့်ချင်ရင်:**

```bash
pip freeze | grep -v "django" > requirements.txt
```

**Django** ကို မထည့်ဘဲ တခြားတွေကိုသာ export မယ်။

---

### **နောက်ဆုံးအကျဉ်းချုပ်**

✅ `pip freeze` — Installed pip packages တွေကို list ပြမယ်။  
✅ `pip freeze > requirements.txt` — Output ကို file ထဲသို့ redirect မယ်။  
✅ `pip freeze >> requirements.txt` — Output ကို overwrite မလုပ်ဘဲ ပေါင်းထည့်မယ်။  
✅ `pip freeze | cut -d "=" -f 1 > requirements.txt` — Version မပါဘဲ export မယ်။

---
