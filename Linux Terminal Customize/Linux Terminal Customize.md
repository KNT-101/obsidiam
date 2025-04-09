
## Terminal Icon  install 

```bash
sudo apt install lsd 
```

### zshrc setup alias 

```bash
alias ls="lsd --icon auto "
```


### ၁။ Font Setup

`lsd` မှာ Nerd Fonts (Powerline Fonts) လိုအပ်ပါတယ်။ Ubuntu based system အတွက် Nerd Fonts ကို install လုပ်ဖို့

```bash
sudo apt install fonts-powerline
```

သို့မဟုတ် Nerd Fonts အပြည့်အစုံကိုရယူဖို့

```bash
sudo apt install fonts-firacode
```

### ၂။ Terminal Font Setting

Terminal Preferences ထဲမှာ Nerd Fonts ကို အသုံးပြုဖို့ပြောင်းပေးပါ။

GNOME Terminal အတွက်

1. `Preferences` > `Profile` > `Text` > `Custom font` ကို ဖွင့်ပါ။
2. `FiraCode Nerd Font` လိုပဲ ရွေးချယ်ပါ။

### ၃။ ZSH Config မှာ Aliases ထည့်ရန်

အကြံပြုချက်အနေဖြင့် `ls` ကို `lsd` နဲ့အစားထိုးရန် `.zshrc` မှာ alias ထည့်နိုင်ပါတယ်။

```bash
alias ls="lsd"
```

ပြီးရင် ZSH ကို reload လုပ်ပါ -

```bash
source ~/.zshrc
```

### ၄။ Icon မပေါ်သေးဘူးလား?

Font မတော်တဆမရသေးဘူးဆိုရင် ဒီသို့လည်းကြိုးစားကြည့်ပါ -

```bash
sudo apt install fonts-nerd
```

---

```bash
# Define colors
RED='\033[31m'
GREEN='\033[32m'
BLUE='\033[34m'
CYAN='\033[36m'
RESET='\033[0m'

# Define the banner function
function print_banner() {
                    printf "${CYAN}                                                                             \n"
                    printf "${RED}██████╗ ██╗   ██╗██████╗ ██╗   ██╗   ██╗   ██████╗ ██╗   ██╗██████╗ ██╗   ██╗\n"
                    printf "${GREEN}██╔══██╗██║   ██║██╔══██╗██║   ██║   ██║   ██╔══██╗██║   ██║██╔══██╗██║   ██║\n"
                    printf "${BLUE}██████╔╝██║   ██║██████╔╝██║   ██║████████╗██║  ██║██║   ██║██║  ██║██║   ██║\n"
                    printf "${CYAN}██╔══██╗██║   ██║██╔══██╗██║   ██║██╔═██╔═╝██║  ██║██║   ██║██║  ██║██║   ██║\n"
                    printf "${RED}██████╔╝╚██████╔╝██████╔╝╚██████╔╝██████║  ██████╔╝╚██████╔╝██████╔╝╚██████╔╝\n"
                    printf "${GREEN}╚═════╝  ╚═════╝ ╚═════╝  ╚═════╝ ╚═════╝  ╚═════╝  ╚═════╝ ╚═════╝  ╚═════╝ \n"
                    printf "${RESET}                                                                             \n"
                    printf "      \e[0m\e[5m\e[1;93m💞  welcom to my Script-cut world Dream. 💞\e[25m\e[0m\n"
                    printf "      \033[0;100m\e[1;92m 󱢴  %s - %s - %s - 󰥔 %s 󱢴 \n" "$(date +'%b')" "$(date +'%d')" "$(date +'%Y')"  "$(date +'%I:%M -%p')"

}

```

```bash
# Custom clear command to include banner
function clear {
    command clear
    # figlet -c -f 3D-ASCII.flf "Love"
    # figlet -c -f slant "Seawolf" 
    #menu_point 
    # print_baner
    print_banner
}
```


