# DevelopmentEnvironmentSetting

## vim (~/.vimrc)
```cmd
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
