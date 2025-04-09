
## 2. SSH=Key ဖန်တီးခြင်း //=//Generate SSH Key Commands line
```
ssh-keygen -t rsa -b 4096 -C "your_emil@example.com"
```

```
Example=======

ssh-keygen -tl rsa -b 4096 -C "kyawnyeinthant2010@gmail.com"

```
<br>

## 3.Add SSH Key To Gitlab Get the public key:SSH Key ကို ကော်ပီယူပါ enter this command

```
cat ~/.ssh/id_rsa.pub
```

<Br>

```
Example === SSH Key 

( ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAACAQDB1zMXOS9P90k/Fr2uOHG9NAxLCjyUyme5Tq9NY5MYhoIy8VvRZhWTfxUrhQL9ebhrpb8SF2PLMooXB6tkYNT6hFWAcv/VyftAkNujyOazOio3pDLVRiYV2b2h0bZX7ZKYhQFf/5D5H1LPUC0OMUtr5pozMbJOMzw5mJjJ4WY+h/yseLosZLQVWaadVWydxRXD/kh71y5To14rhfzI9zAnvrgS6JsFjAzpyH/PQmlnyEpRbQ33UcOtB0Td0ndwyu76YCYFmGnIJZ6Xdg+3hJ4WqEk+GEf3HWmoppnpuMQdNfh4x89e6k66edtdyvTwj087jXzEFPBTdi/hzLkzS15l4Xj8IzDsbIy059E1OUnwPX6UxO7w/BQ1lfnm6l9Sulcw+aoXZFuYWjgKKH7JCO69YDGRXs/fJZI0fnfg+6t/X1+nShVIIjGimqPYk4o2ZqTWILcSX3TjyH3UxRlX7uEBUmoocUm+1H7QjwmMdP4XdJYH6xVdVUso8I/TwwhseU/U2laZW5JhyIIVUw8Flktso9UTXXiEOREr4Fjr03CFFptQsYRxc9ZUgdA6296D3eB/Khc+1DKG1HuOIikWVBw5C5zcxeijHLx4Um/X9Hyc4inlNSUuqiQo6xpFWnuK8R1eoH0nf90px1oySTjP66yjR/iBxb1kTZun+vDk+N7Rcw== kyawnyeinthant2010@gmail.com )
```


<Br>

## 4. log in to Gitlab , navigation to User settings-> SSH Key, and paste the public key on add new key options.

***than your ssh config .***

```
nano ~/.ssh/config
```


***inset plaintext into the code.***

```

"Host gitlab.com
  HostName gitlab.com
  User git
  IdentityFile ~/.ssh/id_rsa"

```


<br>


## 5. Start SSH Key Agent and Add Key== ssh key  ကို  start command // on your terminal 

```
eval "(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa
```


## 6.SSH = key အပ်ပီးရင် နောက်ထပ် cli run ပါ SSH Confirm command on your terminal .

```
ssh -T git@gitlab.com 
yes = ဟုဖြေပါ
```


<br>


## 7. အောက်ပါ cli ဖြင့် remote mod ကို ပြောင်းပါ ။ https ကို print ထုတ်ကြည့်ပါ။

```
git remote -v

git remote set-url origin "your change it gitlab remote reposity"
```

**And them  your terminal on this commands =//နောက်ထပ်git-remote-commandsဖြင့်စစ်ကြည့်ပါကမိမိပြောင်းလိုသောssh-remoteသိုရောက်နေပါလိမ့်မည်။**

```
Example===
"origin git@gitlab.com စတဲ့ http မှ ssh remote သိုပြောင်းသွားပါမည်။"

```

```
git pull

git remote -v 

```

<br>

----

## 8.Git-credentials file create

1. cat ~/.git-credentials ဖြင့် Credential file ကို check လုပ်ကြည့်ပါ။

- cat ~/.git-credentials 

- git config --global credential.helper store

- nano ~/.git-credentials

(nano(etc..text,editor) ~/.git-credentials (text-editor တစ်ခုခုဖြင့်ဖွင့်ပါ /// )

(Example ====== code အဆိုပါ နမူနာမျိုးဖြင့်ထည့်ပါ )

```
"https://kyawnyeinthant2024:glpat-3v2fkU8YdqJzrXypMdEz@gitlab.com"

```






# Git Credential Helper (Permanent Storage Mode)

1. . Permanent credentials storagegit config --global credential.helper store

- .git-credentials ဖိုင်ကို ဖန်တီးခြင်းနှင့် တည်ဆောက်ခြင်း

- git-credentials ဖိုင်ကို သင့် user home directory တွင်ဖန်တီးပါ။

- nano ~/.git-credentials ဖိုင်ထဲတွင် သင်၏ GitLab personal access token ကို သွင်းပါ။

- https://<your_username><your_personal_access_token>@gitlab.com


#### 2. ရှင်းလင်းချက်။

<your_username> ကို သင်၏ GitLab username ဖြင့် အစားထိုးပါ။

<your_personal_access_token> ကို သင်၏ GitLab personal access token ဖြင့် အစားထိုးပါ။


Example - 
- .git-credentialsဖိုင်https://your_username:your_personal_access_token@gitlab.com

- GitLab Personal Access Token ကို ဖန်တီးခြင်း

- GitLab တွင် login ဝင်ပါ။Profile Settings -> Access Tokens သို့ သွားပါ။

- Token အတွက် အမည်ထည့်ပါ၊ သက်တမ်းကုန်ဆုံးရက်ကို သတ်မှတ်ပါ။လိုအပ်သော scopes များကို ရွေးပါ၊

- ဥပမာ api, read_repository, write_repository စသည်။Create personal access token ကို နှိပ်ပါ၊ Token ကို ကူးယူပါ။

<br>




