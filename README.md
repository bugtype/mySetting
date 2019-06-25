# mySetting
내 셋팅 모음


[TOC]

## Chrome

## VS code

## mac

### terminal ( ~/.zshrc )

```bash

alias vimz="vim ~/.zshrc"

alias code="/Applications/Visual\ Studio\ Code.app/Contents/Resources/app/bin/code"
code () { VSCODE_CWD="$PWD" open -n -b "com.microsoft.VSCode" --args $* ;}

alias gitlogs="git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --a    bbrev-commit"



alias gitweek="git log --pretty=format:'%C(green)%h %C(reset) %an %C(blue) %ar %C(reset), %C(white) %s' --since='1 week ago'"
 
```

### terminal

## alias


.gitconfig


```bash
[alias]
    s = status -s
    pm = "!curr=$(git rev-parse --abbrev-ref HEAD) &&  git checkout master && git pull && git checkout $curr"
    pd = "!curr=$(git rev-parse --abbrev-ref HEAD) &&  git checkout develop && git pull && git checkout $curr"
    a = "! # add files with fzf preview diffs; \n\
        f() { \
            _height=$(stty size | awk '{print $1}');\
            git s | fzf -m --preview \"git diff {2} | head -n $_height | pygmentize\" | awk '{print $2}' | xargs git add; \
        }; f"
    ch = "!git checkout $(git bselect)"
    bselect = "! # select branch with preview; \n\
        f() { \
            _height=$(stty size | awk '{print $1}');\
            git branch | egrep -v '^\\*' | fzf --preview \"git l {1} | head -n $_height\"; \
        }; f"
    alias = "!git config --list | egrep '^alias.+'"
    
```


## tool

# 컨벤션

## git commit

## eslint
