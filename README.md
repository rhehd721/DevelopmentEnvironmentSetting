# DevelopmentEnvironmentSetting

## MAC mouse scaling
```cmd
defaults read .GlobalPreferences com.apple.mouse.scaling	// 현재 감도 확인

defaults write .GlobalPreferences com.apple.mouse.scaling 5	// 감도 변경
```

## install
- tftpd64
- Tera Term
- Wireshark

## vim (~/.vimrc)
```cmd
// mac
set nocompatible    " Vim 디폴트 기능들을 사용함

set backspace=2     " 삽입 모드에서 백스페이스를 계속 허용

set autoindent      " 자동 들여쓰기

set cindent         " c언어 자동 들여쓰기

set smartindent     " 자동 들여쓰기

set textwidth=76    " 76번째 칸을 넘어가면 자동으로 줄 바꿈

set nowrapscan      " 찾기에서 파일의 맨 끝에 이르면 계속하여 찾지 않음

set nobackup       " 백업파일을 만들지 않음

set novisualbell    " 비주얼벨 기능을 사용하지 않음

set nojoinspaces    " J 명령어로 줄을 붙일 때 마침표 뒤에 한칸만 띔

set ruler           " 상태 표시줄에 커서 위치를 표시

set tabstop=4       " 탭간격

set shiftwidth=4    " 자동 들여쓰기 간격

set keywordprg=edic    " K를 눌렀을 때 실행할 명령어

set showcmd         " (부분적인) 명령어를 상태라인에 보여줌

set showmatch       " 매치도는 괄호의 반대쪽을 보여줌

set ignorecase      " 찾기에서 대/소문자를 구별하지 않음

set incsearch       " 점진적으로 찾기

set autowrite       " :next나 :make같은 명령을 입력하면 자동으로 저장

set title           " 타이틀바에 현재 편집중인 파일을 표시

set nu              " 라인번호

set enc=UTF-8       " 인코딩

set fileencodings=UTF-8 " 파일 인코딩 UTF-8

syntax on           " 문법 강조기능
```
```cmd
// window
if has("syntax")    # 문법 강조(색상)
    syntax on
endif

set hlsearch    # 검색문자 강조
set nu  # 줄번호
set autoindent  # 들여쓰기
set ts=4    # '\t' 값을 출력시 몇 개의 스페이스로 보여줄지
set sts=4   # tab 키를 눌렀을 때 몇 개의 스페이스를 입력할 것인지
set cindent
set laststatus=2
set shiftwidth=4
set showmatch   # 괄호 하이라이트
set smartcase   # 검색, 탭, 들여쓰기 시 자동으로 설정
set smarttab    # 검색, 탭, 들여쓰기 시 자동으로 설정
set smartindent # 검색, 탭, 들여쓰기 시 자동으로 설정
set ruler   # 커서 위치의 줄번호와 행번호 출력
set fileencodings=utf8,euc-kr   # 인코딩
```

## bat
```bat
@setlocal enableextensions enabledelayedexpansion
@echo off

set state="success"
set filename="Z:\EasyMESH\done"
set src_filename="Z:\EasyMESH\index.html"
set dst_filename="C:\download\index.html"

pause

:loop


           cls
           COLOR 07
           echo ####################################################
           echo #### READY      Name                                  ###
           echo ####################################################       
           pause

	
	echo yes | copy  "Z:\EasyMESH\index.html"   "D:\"
	
  	timeout 3         
   
                      
goto :loop

del C:\download\index.html

```

## Linux_command (~/.bashrc)
```cmd
alias svndiff="svn diff | awk '/^Index/ {print $NF}'"
alias c="clear"
alias ff="grep -rn --exclude='*.svn-base'"
alias gg="find -name"
alias rr="rm -rf"
```
## ArpCheck.sh
```sh
#!/bin/sh

success=no
ret="init"

arping -I $2 -c 1 -w 1 $1 >/dev/null
#arping -I brwan -c 1 -w 1 $192.168.123.100

ret="$?"

if [ $ret == 0 ]; then
        success=yes
else
        success=no
        break
fi

if [ "$success" = "yes" ]; then
        echo 'SUCCESS'
        return 0
else
        echo 'FAIL'
        return 1
fi
```
## rdisc6
```sh
system("rm -f /var/rdisc_httpd");
system("rdisc6 -w 1000 -r 1 ff02::2 eth0.1 | grep -c 'Router' >  /var/rdisc_httpd");

FILE *fp = fopen("/var/rdisc_httpd", "r");
```
