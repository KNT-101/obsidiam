
# Git-Cheat-Sheet

## Configuration (ပြုပြင်မှုပုံစံများ)
| Command | Description |
| - | - |
| `git config --global user.name "foo"`              | အသုံးပြုသူအမည်ကို သတ်မှတ်ပါ |
| `git config --global user.email "foo@example.com"` | အသုံးပြုသူအီးမေးလ်ကို သတ်မှတ်ပါ |

## Branches (ဘရန်ချ်များ)
| Command | Description |
| - | - |
| `git branch foo`                          | ဘရန်ချ် အသစ်တစ်ခု ဖန်တီးပါ |
| `git branch -d foo`                       | ဘရန်ချ်ကို ဖျက်ပါ |
| `git switch foo`                          | ဘရန်ချ်သို့ ပြောင်းပါ |
| `git switch -c\|--create foo`             | ဘရန်ချ် အသစ်ဖန်တီးပြီး ပြောင်းပါ |
| `git restore foo.js`                      | foo.js ဖိုင်ပေါ်မှာ လုပ်ထားသော အပြုပြင်များအားလုံးကို ပြန်လည်မရှိအောင်လုပ်ပါ |
| `git checkout foo.js`                     | foo.js ဖိုင်ပေါ်မှာ လုပ်ထားသော အပြုပြင်များအားလုံးကို ပြန်လည်မရှိအောင်လုပ်ပါ |
| `git checkout foo`                        | `git switch` ကို အသုံးပြုပါ |
| `git checkout -b foo`                     | `git switch -c` ကို အသုံးပြုပါ |
| `git merge foo`                           | ဘရန်ချ်ကို လက်ရှိ ဘရန်ချ်တွင် ပေါင်းထည့်ပါ |

## Pulling (ဆွဲယူခြင်း)
| Command | Description |
| - | - |
| `git pull --rebase --prune`               | နောက်ဆုံးဗားရှင်းကို ဆွဲယူပြီး၊ မရောထွေးသေးသော အပြုပြင်များကို ပြန်လည်သုံးပါ၊ ရှိမနေသော ဘရန်ချ်များကို ဖျက်ပါ |

## Staged Changes (အဆင့်မြှင့်အပြုပြင်များ)
| Command | Description |
| - | - |
| `git add file.txt`                        | ဖိုင်ကို အဆင့်မြှင့်ပါ |
| `git add -p\|--patch file.txt`            | ဖိုင်ထဲမှာ အပြုပြင်အချို့ကိုသာ အဆင့်မြှင့်ပါ |
| `git mv file1.txt file2.txt`              | ဖိုင်ကို ရွှေ့ပါ/အမည်ပြောင်းပါ |
| `git rm --cached file.txt`                | ဖိုင်ကို အဆင့်မြှင့်မှ ပြန်ရင်ဆောင်ပါ |
| `git rm --force file.txt`                 | ဖိုင်ကို အဆင့်မြှင့်ပြီး ဖျက်ပါ |
| `git reset HEAD`                          | အပြုပြင်များကို အဆင့်မြှင့်မှ ပြန်ရင်ဆောင်ပါ |
| `git reset --hard HEAD`                   | အပြုပြင်များကို အဆင့်မြှင့်ပြီး ဖျက်ပါ |
| `git clean -f\|--force -d`                | လုပ်ငန်းစဉ်ပတ်ဝန်းကျင်ထဲမှ အပြောအဆိုမပါသော ဖိုင်များကို အထက်ပါနေရာမှ ဖျက်ပါ |
| `git clean -f\|--force -d -x`             | အပြောအဆိုမပါသော နှင့် ငြင်းဆိုထားသော ဖိုင်များကို အထက်ပါနေရာမှ ဖျက်ပါ |

## Changing Commits (ကော်မစ်ပြောင်းလဲခြင်း)
| Command | Description |
| - | - |
| `git reset 5720fdf`                           | လက်ရှိ ဘရန်ချ်ကို အလုပ်ဆောင်ရုံသာ ပြန်လည်လုပ်ပါ (working area မသုံးပါ) |
| `git reset HEAD~1`                            | လက်ရှိ ဘရန်ချ်ကို မူလက commit အထိ ပြန်လည်လုပ်ပါ |
| `git reset --hard 5720fdf`                    | လက်ရှိ ဘရန်ချ်နှင့် အလုပ်ဆောင်ရုံကို ကော်မစ်အထိ ပြန်လည်လုပ်ပါ |
| `git commit --amend -m "New message"`         | နောက်ဆုံး ကော်မစ်၏ မက်ဆေ့ခ်ျကို ပြောင်းပါ |
| `git commit --fixup 5720fdf -m "New message"` | သတ်မှတ်ထားသော ကော်မစ်တွင် ပေါင်းထည့်ပါ |
| `git revert 5720fdf`                          | ကော်မစ်ကို ပြန်လည်လုပ်ပါ |
| `git rebase --interactive [origin/main]`      | PR ကို ရှိသော အချိန်မှာ `git pull` ပြီးမှ rebasing လုပ်ပါ |
| `git rebase --interactive 5720fdf`            | သတ်မှတ်ထားသော ကော်မစ်အထိ rebasing လုပ်ပါ |
| `git rebase --interactive --root 5720fdf`     | မူလက commit အထိ rebasing လုပ်ပါ |
| `git rebase --continue`                       | interactive rebase ကို ဆက်လက်လုပ်ပါ |
| `git rebase --abort`                          | interactive rebase ကို ပယ်ဖျက်ပါ |
| `git cherry-pick 5720fdf`                     | ကော်မစ်ကို လက်ရှိ ဘရန်ချ်သို့ ကူးယူပါ |

## Compare (နှိုင်းယှဉ်ခြင်း)
| Command | Description |
| - | - |
| `git diff`                                | လက်ရှိ ဘရန်ချ်နှင့် အလုပ်ဆောင်ရုံအကြား အထူးချက်များကို ကြည့်ပါ |
| `git diff HEAD HEAD~2`                    | လက်ရှိ ကော်မစ်နှင့် နှစ်ခုအရင်က ကော်မစ်များအကြား အထူးချက်များကို ကြည့်ပါ |
| `git diff main other`                     | ဘရန်ချ် နှစ်ခုကြား အထူးချက်များကို ကြည့်ပါ |

## View (ကြည့်ရှုခြင်း)
| Command | Description |
| - | - |
| `git log`                                 | ကော်မစ်စာရင်းကို ကြည့်ပါ |
| `git log --patch`                         | ကော်မစ်စာရင်းနှင့် အလိုက်နောက်ခံပြောင်းလဲမှုများကို ကြည့်ပါ |
| `git log --decorate --graph --oneline`    | ကော်မစ်ကို ကြည့်ရှုနိုင်သော အတွင်းအမြင်ကို ကြည့်ပါ |
| `git log --grep foo`                      | foo ဆိုသော စာသားပါသော ကော်မစ်များကို ကြည့်ပါ |
| `git show HEAD`                           | လက်ရှိ ကော်မစ်ကို ပြပါ |
| `git show HEAD^` or `git show HEAD~1`     | ယခင် ကော်မစ်ကို ပြပါ |
| `git show HEAD^^` or `git show HEAD~2`    | နှစ်ခုအရင်က ကော်မစ်ကို ပြပါ |
| `git show main`                           | ဘရန်ချ်အတွင်း အဆုံးသတ် ကော်မစ်ကို ပြပါ |
| `git show 5720fdf`                        | သတ်မှတ်ထားသော ကော်မစ်ကို ပြပါ |
| `git blame file.txt`                      | ဘယ်သူပြင်ခဲ့ပြီး ဘယ်အချိန်တွင် ပြင်ခဲ့သည်ကို ကြည့်ပါ |

## Stash (သိုလှောင်ခြင်း)
| Command | Description |
| - | - |
| `git stash push -m "Message"`             | အဆင့်မြှင့်ထားသော ဖိုင်များကို သိုလှောင်ပါ |
| `git stash --include-untracked`           | အလုပ်ဆောင်ရုံနှင့် အဆင့်မြှင့်ထားသော ဖိုင်များကို သိုလှောင်ပါ |
| `git stash --staged`                      | အဆင့်မြှင့်ထားသော ဖိုင်များကို သိုလှောင်ပါ |
| `git stash list`                          | သိုလှောင်ထားသော ပစ္စည်းများကို စာရင်းပြပါ |
| `git stash apply`                         | နောက်ဆုံးသိုလှောင်ထားသော ပစ္စည်းကို အလုပ်ဆောင်ရုံသို့ ပြန်လည်မရှိအောင်လုပ်ပါ |
| `git stash apply 0`                       | သတ်မှတ်ထားသော သိုလှောင်ထားသော ပစ္စည်းကို အလုပ်ဆောင်ရုံသို့ ပြန်လည်မရှိအောင်လုပ်ပါ |
| `git stash clear`                         | သိုလှောင်ထားသော ပစ္စည်းများကို ဖျက်ပါ |

## Tags (တံဆိပ်များ)
| Command | Description |
| - | - |
| `git tag`                                              | အားလုံးသော တံဆိပ်များကို စာရင်းပြပါ |
| `git tag -a\|--annotate 0.0.1 -m\|--message "Message"` | တံဆိပ်အသစ်တစ်ခု ဖန်တီးပါ |
| `git tag -d\|--delete 0.0.1`
## Remote (ဌားမူများ)
| Command | Description |
| - | - |
| `git remote -v`                           | ဌားမူများကို စာရင်းပြပါ |
| `git remote show origin`                  | ဌားမူတစ်ခု၏ အသေးစိတ်အချက်အလက်များကို ပြပါ |
| `git remote add upstream <url>`           | ဌားမူ upstream repository ကို ပေါင်းထည့်ပါ |
| `git fetch upstream`                      | အားလုံးသော ဌားမူ ဘရန်ချ်များကို fetch လုပ်ပါ |
| `git rebase upstream/main`                | main branch ကို upstream မှ ပြန်လည်ထိန်းသိမ်းပါ |
| `git push --force`                        | မည်သည့်ပြင်ဆင်မှုများကိုမဆို ပို့ပြီး၊ ဌားမူပြောင်းလဲမှုများကို ကျန်ထားပါ |
| `git push --force-with-lease`             | မည်သည့်ပြင်ဆင်မှုများကိုမဆို ပို့ပြီး၊ ဌားမူပြောင်းလဲမှုများရှိပါက ပယ်ဖျက်ပါ |
| `git push --tags`                         | ဌားမူများကို remote repository သို့ ပို့ပါ |

## Submodules (အဖွဲ့အစည်းများ)
| Command | Description |
| - | - |
| `git submodule status`                    | အားလုံးသော အဖွဲ့အစည်းများ၏ အခြေအနေကို စစ်ဆေးပါ |

- Submodules ကို ဆွဲယူပါ
  1. `git submodule sync`
  2. `git submodule init`
  3. `git submodule update`

- Branch ပြောင်းပါ
  1. `cd /submodule`
  2. `git fetch origin <branch-name>`
  3. `git checkout <branch-name>`
  4. `cd /`


---

## Configuration (ပြုပြင်မှုပုံစံများ)
| Command | Description |
| - | - |
| `git config --global user.name "foo"`              | အသုံးပြုသူအမည်ကို သတ်မှတ်ပါ |
| `git config --global user.email "foo@example.com"` | အသုံးပြုသူအီးမေးလ်ကို သတ်မှတ်ပါ |

## Branches (ဘရန်ချ်များ)
| Command | Description |
| - | - |
| `git branch foo`                          | ဘရန်ချ် အသစ်တစ်ခု ဖန်တီးပါ |
| `git branch -d foo`                       | ဘရန်ချ်ကို ဖျက်ပါ |
| `git switch foo`                          | ဘရန်ချ်သို့ ပြောင်းပါ |
| `git switch -c\|--create foo`             | ဘရန်ချ် အသစ်ဖန်တီးပြီး ပြောင်းပါ |
| `git restore foo.js`                      | foo.js ဖိုင်ပေါ်မှာ လုပ်ထားသော အပြုပြင်များအားလုံးကို ပြန်လည်မရှိအောင်လုပ်ပါ |
| `git checkout foo.js`                     | foo.js ဖိုင်ပေါ်မှာ လုပ်ထားသော အပြုပြင်များအားလုံးကို ပြန်လည်မရှိအောင်လုပ်ပါ |
| `git checkout foo`                        | `git switch` ကို အသုံးပြုပါ |
| `git checkout -b foo`                     | `git switch -c` ကို အသုံးပြုပါ |
| `git merge foo`                           | ဘရန်ချ်ကို လက်ရှိ ဘရန်ချ်တွင် ပေါင်းထည့်ပါ |

## Pulling (ဆွဲယူခြင်း)
| Command | Description |
| - | - |
| `git pull --rebase --prune`               | နောက်ဆုံးဗားရှင်းကို ဆွဲယူပြီး၊ မရောထွေးသေးသော အပြုပြင်များကို ပြန်လည်သုံးပါ၊ ရှိမနေသော ဘရန်ချ်များကို ဖျက်ပါ |

## Staged Changes (အဆင့်မြှင့်အပြုပြင်များ)
| Command | Description |
| - | - |
| `git add file.txt`                        | ဖိုင်ကို အဆင့်မြှင့်ပါ |
| `git add -p\|--patch file.txt`            | ဖိုင်ထဲမှာ အပြုပြင်အချို့ကိုသာ အဆင့်မြှင့်ပါ |
| `git mv file1.txt file2.txt`              | ဖိုင်ကို ရွှေ့ပါ/အမည်ပြောင်းပါ |
| `git rm --cached file.txt`                | ဖိုင်ကို အဆင့်မြှင့်မှ ပြန်ရင်ဆောင်ပါ |
| `git rm --force file.txt`                 | ဖိုင်ကို အဆင့်မြှင့်ပြီး ဖျက်ပါ |
| `git reset HEAD`                          | အပြုပြင်များကို အဆင့်မြှင့်မှ ပြန်ရင်ဆောင်ပါ |
| `git reset --hard HEAD`                   | အပြုပြင်များကို အဆင့်မြှင့်ပြီး ဖျက်ပါ |
| `git clean -f\|--force -d`                | လုပ်ငန်းစဉ်ပတ်ဝန်းကျင်ထဲမှ အပြောအဆိုမပါသော ဖိုင်များကို အထက်ပါနေရာမှ ဖျက်ပါ |
| `git clean -f\|--force -d -x`             | အပြောအဆိုမပါသော နှင့် ငြင်းဆိုထားသော ဖိုင်များကို အထက်ပါနေရာမှ ဖျက်ပါ |

## Changing Commits (ကော်မစ်ပြောင်းလဲခြင်း)
| Command | Description |
| - | - |
| `git reset 5720fdf`                           | လက်ရှိ ဘရန်ချ်ကို အလုပ်ဆောင်ရုံသာ ပြန်လည်လုပ်ပါ (working area မသုံးပါ) |
| `git reset HEAD~1`                            | လက်ရှိ ဘရန်ချ်ကို မူလက commit အထိ ပြန်လည်လုပ်ပါ |
| `git reset --hard 5720fdf`                    | လက်ရှိ ဘရန်ချ်နှင့် အလုပ်ဆောင်ရုံကို ကော်မစ်အထိ ပြန်လည်လုပ်ပါ |
| `git commit --amend -m "New message"`         | နောက်ဆုံး ကော်မစ်၏ မက်ဆေ့ခ်ျကို ပြောင်းပါ |
| `git commit --fixup 5720fdf -m "New message"` | သတ်မှတ်ထားသော ကော်မစ်တွင် ပေါင်းထည့်ပါ |

---

# Git Checksheet (မြန်မာ)

## အခြေခံ Git Commands

### Repository တည်ဆောက်ခြင်း
- **git init**  
  အသစ်တည်ဆောက်မည့် repository အတွက်:
  ```sh
  git init
  ```

### Repository Clone ပြုလုပ်ခြင်း
- **git clone**  
  Remote repository ကို local သို့ clone လုပ်ရန်:
  ```sh
  git clone [repository URL]
  ```

### File အပြောင်းအလဲများ Check
- **git status**  
  File များ၏ အခြေအနေစစ်ဆေးရန်:
  ```sh
  git status
  ```

### File များ Add ပြုလုပ်ခြင်း
- **git add**  
  File များကို stage ပေးရန်:
  ```sh
  git add [file]
  ```
  (သို့) ဖိုင်အားလုံးကို add ပြုလုပ်ရန်:
  ```sh
  git add .
  ```

### Commit ပြုလုပ်ခြင်း
- **git commit**  
  Changes များကို commit ပြုလုပ်ရန်:
  ```sh
  git commit -m "Commit message"
  ```

### Changes များ Push ပြုလုပ်ခြင်း
- **git push**  
  Local changes များကို remote repository သို့ push ပြုလုပ်ရန်:
  ```sh
  git push origin [branch-name]
  ```

### Changes များ Pull ပြုလုပ်ခြင်း
- **git pull**  
  Remote repository မှ changes များကို pull ပြုလုပ်ရန်:
  ```sh
  git pull origin [branch-name]
  ```

### Branches အလုပ်လုပ်ခြင်း
- **git branch**  
  Branch များ၏ စာရင်းကိုကြည့်ရန်:
  ```sh
  git branch
  ```

- **git checkout**  
  အခြား branch သို့ပြောင်းရန်:
  ```sh
  git checkout [branch-name]
  ```

- **git checkout -b**  
  အသစ် branch တစ်ခုဖန်တီးပြီး ပြောင်းရန်:
  ```sh
  git checkout -b [new-branch-name]
  ```

### Merge ပြုလုပ်ခြင်း
- **git merge**  
  Branch များကို merge ပြုလုပ်ရန်:
  ```sh
  git merge [branch-name]
  ```

### Tag တွဲခြင်း
- **git tag**  
  အမှတ်အသား တစ်ခုချသည်:
  ```sh
  git tag [tag-name]
  ```

### Log ကြည့်ခြင်း
- **git log**  
  Commit များ၏ အကြောင်းအရာကိုကြည့်ရန်:
  ```sh
  git log
  ```

### Remote ကိုစီမံခြင်း
- **git remote add**  
  Remote repository ကို add လုပ်ရန်:
  ```sh
  git remote add origin [repository URL]
  ```

- **git remote -v**  
  Remote repository များကိုကြည့်ရန်:
  ```sh
  git remote -v
  ```

## အကျိုးရှိစေမည့် Git Tips
- **.gitignore ဖိုင် အသုံးပြုခြင်း**  
  Git တွင် track မလုပ်စေရန် file များကို .gitignore ဖိုင်တွင် ဖော်ပြပါ။

- **git stash**  
  လုပ်နေသော changes များကို ယာယီသိမ်းထားရန်:
  ```sh
  git stash
  ```

- **git stash pop**  
  ယာယီသိမ်းထားသော changes များကို ပြန်ထုတ်ရန်:
  ```sh
  git stash pop
  ```

## နောက်ဆုံးသတ်မှတ်ချက်များ
Git သည် Version Control System ဖြစ်ပြီး၊ ဖိုင်များကို စီမံခန့်ခွဲရန် အလွန်အကျိုးရှိသည်။ အထက်ပါ commands များကို အသုံးပြုခြင်းဖြင့် သင်၏ project များကို လွယ်ကူစွာစီမံနိုင်သည်။

---

# Git-Cheat-Sheet
A cheat sheet for uncommon Git commands

## Configuration
| Command | Description |
| - | - |
| `git config --global user.name "foo"`              | Set user name |
| `git config --global user.email "foo@example.com"` | Set user email |

## Branches
| Command | Description |
| - | - |
| `git branch foo`                          | Create a new branch |
| `git branch -d foo`                       | Deletes a branch |
| `git switch foo`                          | Switch to a branch |
| `git switch -c\|--create foo`             | Create and switch to a branch |
| `git restore foo.js`                      | Undo all changes on the foo.js file |
| `git checkout foo.js`                     | Undo all changes on the foo.js file |
| `git checkout foo`                        | Use `git switch` instead |
| `git checkout -b foo`                     | Use `git switch -c` instead |
| `git merge foo`                           | Merge branch into current branch |

## Pulling
| Command | Description |
| - | - |
| `git pull --rebase --prune`               | Get latest, rebase any changes not checked in and delete branches that no longer exist | 

## Staged Changes
| Command | Description |
| - | - |
| `git add file.txt`                        | Stage file |
| `git add -p`|--patch file.txt`            | Stage some but not all changes in a file |
| `git mv file1.txt file2.txt`              | Move/rename file |
| `git rm --cached file.txt`                | Unstage file |
| `git rm --force file.txt`                 | Unstage and delete file |
| `git reset HEAD`                          | Unstage changes |
| `git reset --hard HEAD`                   | Unstage and delete changes |
| `git clean -f\|--force -d`                | Recursively remove untracked files from the working tree |
| `git clean -f\|--force -d -x`             | Recursively remove untracked and ignored files from the working tree |

## Changing Commits
| Command | Description |
| - | - |
| `git reset 5720fdf`                           | Reset current branch but not working area to commit |
| `git reset HEAD~1`                            | Reset the current branch but not working area to the previous commit |
| `git reset --hard 5720fdf`                    | Reset current branch and working area to commit |
| `git commit --amend -m "New message"`         | Change the last commit message |
| `git commit --fixup 5720fdf -m "New message"` | Merge into the specified commit |
| `git revert 5720fdf`                          | Revert a commit |
| `git rebase --interactive [origin/main]`      | Rebase a PR (`git pull` first) |
| `git rebase --interactive 5720fdf`            | Rebase to a particular commit |
| `git rebase --interactive --root 5720fdf`     | Rebase to the root commit |
| `git rebase --continue`                       | Continue an interactive rebase |
| `git rebase --abort`                          | Cancel an interactive rebase |
| `git cherry-pick 5720fdf`                     | Copy the commit to the current branch |

## Compare
| Command | Description |
| - | - |
| `git diff`                                | See difference between working area and current branch |
| `git diff HEAD HEAD~2`                    | See difference between te current commit and two previous commits |
| `git diff main other`                     | See difference between two branches |

## View
| Command | Description |
| - | - |
| `git log`                                 | See commit list |
| `git log --patch`                         | See commit list and line changes |
| `git log --decorate --graph --oneline`    | See commit visualization |
| `git log --grep foo`                      | See commits with foo in the message |
| `git show HEAD`                           | Show the current commit |
| `git show HEAD^` or `git show HEAD~1`     | Show the previous commit |
| `git show HEAD^^` or `git show HEAD~2`    | Show the commit going back two commits |
| `git show main`                           | Show the last commit in a branch |
| `git show 5720fdf`                        | Show named commit |
| `git blame file.txt`                      | See who changed each line and when |

## Stash
| Command | Description |
| - | - |
| `git stash push -m "Message"`             | Stash staged files |
| `git stash --include-untracked`           | Stash working area and staged files |
| `git stash --staged`                      | Stash staged files |
| `git stash list`                          | List stashes |
| `git stash apply`                         | Moved last stash to working area |
| `git stash apply 0`                       | Moved named stash to working area |
| `git stash clear`                         | Clear the stash |

## Tags
| Command | Description |
| - | - |
| `git tag`                                              | List all tags |
| `git tag -a\|--annotate 0.0.1 -m\|--message "Message"` | Create a tag |
| `git tag -d\|--delete 0.0.1`                           | Delete a tag |
| `git push --tags`                                      | Push tags to remote repository |

## Remote
| Command | Description |
| - | - |
| `git remote -v`                           | List remote repositories |
| `git remote show origin`                  | Show remote repository details |
| `git remote add upstream <url>`           | Add remote upstream repository |
| `git fetch upstream`                      | Fetch all remote branches |
| `git rebase upstream/main`                | Refresh main branch from upstream |
| `git remote -v`                           | List remote repositories |
| `git push --force`                        | Push any changes while overwriting any remote changes |
| `git push --force-with-lease`             | Push any changes but stop if there are any remote changes |
| `git push --tags`                         | Push tags to remote repository |

## Submodules
| Command | Description |
| - | - |
| `git submodule status`                    | Check status of all submodules |

- Pull submodules
  1. `git submodule sync`
  2. `git submodule init`
  3. `git submodule update`
- Change branch
  1. `cd /submodule`
  2. `git fetch origin <branch-name>`
  3. `git checkout <branch-name>`
  4. `cd /`

---

