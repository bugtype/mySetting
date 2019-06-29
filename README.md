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


## git commit

## eslint



## spring boot / java 셋팅

```bash
brew install maven

brew tap adoptopenjdk/openjdk
brew cask install adoptopenjdk8 adoptopenjdk11

jenv add /Library/Java/JavaVirtualMachines/adoptopenjdk-11.jdk/Contents/Home
jenv add /Library/Java/JavaVirtualMachines/adoptopenjdk-8.jdk/Contents/Home

#가지고 있는 자바 버젼 확인
/usr/libexec/java_home -v 

# ~/.zshrc에 넣어야함
if which jenv > /dev/null; then eval "$(jenv init -)"; fi
export JAVA_HOME=$HOME/.jenv/versions/$(jenv version-name)

# 넣고나서 source로 실행
source ~/.zhsrc

# version 확인
echo $JAVA_HOME
jenv versions


jenv global openjdk64-1.8.0.212 && jenv versions

```
path: /Library/Java/JavaVirtualMachines/

jdk: https://github.com/AdoptOpenJDK/homebrew-openjdk

setting: https://start.spring.io/

참고: https://advenoh.tistory.com/20
