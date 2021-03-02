# mySetting
내 셋팅 모음


[TOC]

## Chrome

## VS code 플러그인

https://velog.io/@rtyu1120/%EB%82%B4%EA%B0%80-%EC%93%B0%EB%8A%94-Visual-Studio-Code-%EC%9D%B5%EC%8A%A4%ED%85%90%EC%85%98-%EB%AA%A8%EC%9D%8C%EC%A7%91-kmjtvc7xp8

https://junhobaik.github.io/vsc-plugin-list/

### terminal ( ~/.zshrc )

```bash

alias vimz="vim ~/.zshrc"

# vs code가 안될떄 셋팅
alias code="/Applications/Visual\ Studio\ Code.app/Contents/Resources/app/bin/code"
code () { VSCODE_CWD="$PWD" open -n -b "com.microsoft.VSCode" --args $* ;}

 
```

## git alias


.gitconfig


개인적으로 alias에다가 push 관련 스크립트는 넣지 않는다. 사람은 실수를 하므로...

```bash
brew install fzf
pip3 install pygments

```

```bash
[alias]
    s = status -s
    week="git log --pretty=format:'%C(green)%h %C(reset) %an %C(blue) %ar %C(reset), %C(white) %s' --since='1 week ago'"
    logs="git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --a    bbrev-commit"
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
    branch-remote = "!f() { git checkout -b \"$1\" \"remotes/origin/$1\"; }; f"
    push-u = "!git push --set-upstream upstream \"$(git rev-parse --abbrev-ref HEAD)\""
    push-o = "!git push --set-upstream origin \"$(git rev-parse --abbrev-ref HEAD)\""
    alias = "!git config --list | egrep '^alias.+'"
    
```


## tool


## git commit

## eslint 


.eslintrc

```javascript
{
  "env": {
    "node": true,
    "es6": true
  },
  "extends": "airbnb"
}
```

## React-native (RN)

### 주의

react-redux는 6.0.1을 이용해야 한다.
```
npm i --save react-redux@6.0.1.
expo r -c
```

설치 
```
npm i # 먼저 한다.
pod install # 한다
```

안될 시
```
Android Studio / Xcode에서 실행해 본다.
```

### android

1. react-native-cli 설치
2. react-native init 폴더명 으로 생성
3. 생성된 RN 프로젝트에 있는 안드로이드 폴더에 local.properties 생성 후 sdk.dir 추가 후 저장

- sdk.dir=C\:\\Users\\L\\AppData\\Local\\Android\\Sdk

4. 환경변수 ANDROID_HOME 설정 - RN 실행 용도

- C:\Users\L\AppData\Local\Android\Sdk\

5. 환경변수 PATH 설정 - adb 연결 용도

- C:\Users\L\AppData\Local\Android\Sdk\platform-tools

6. react-native run-android 로 실행
7. adb devices 로 폰이 usb 연결되어 있는지 확인
8. adb servce tcp:8081 tcp:8081 입력해서 연결
9. react-native start로 실행
10. 설치된 앱을 실행하면 자동으로 hot loader가 된다.

#### typescript

1. 설치

- npm install typescript @types/react @types/react-native --save-dev

2. tsconfig.json 만들기

```
{
  "compilerOptions": {
    "target": "es2015",
    "module": "commonjs",
    "moduleResolution": "node",
    "noResolve": false,
    "noImplicitAny": false,
    "removeComments": false,
    "allowJs": true,
    "jsx": "react",
    "allowSyntheticDefaultImports": true,
    "typeRoots": ["./node_modules/@types", "./src/@types"]
  },
  "exclude": [
    "node_modules",
    "dest",
    "android",
    "ios",
    "acceptance-tests",
    ".jest",
    "src/setupTests.ts",
    "./node_modules/**/*"
  ],
  "include": ["./node_modules/@types", "./src/**/*", "./src/@types"]
}

```

귀찮으면 걍 아래껄로 입력
react-native init MyApp --template typescript

https://github.com/microsoft/TypeScript-React-Native-Starter

### tslint.json

```
{
    "extends": [],
    "defaultSeverity": "warning",
    "linterOptions": {
      "exclude": [
        "config/**/*.js",
        "node_modules/**/*.ts"
      ]
    }
}
```


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


