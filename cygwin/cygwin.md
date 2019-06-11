## 安裝 Cygwin

https://cygwin.com/install.html 下載setup-x86_64.exe

![](/img/2019-04-01_150802.png ':no-zoom')

執行下載的檔案setup-x86_64.exe，點擊下一步。

![](/img/2019-04-01_150741.png ':no-zoom')

選擇第一個選項 Install from internet (所有套件從網路下載)，點擊下一步。

![](/img/2019-04-01_150844.png ':no-zoom')

選擇安裝的資料夾，Install For 選擇 All (所有使用者都可以使用)，點擊下一步。

![](/img/2019-04-01_151234.png ':no-zoom')

選擇下載套件要存放的資料夾，所有下載的套件都會存放在此，點擊下一步。

![](/img/2019-04-01_151312.png ':no-zoom')

網路環境是否使用 Proxy 下載，我這邊不使用所以選擇第一項，點擊下一步。

![](/img/2019-04-01_151333.png ':no-zoom')

選擇要下載的伺服器，台灣伺服器在元智大學。

![](/img/2019-04-01_151347.png ':no-zoom')

進入套件選擇視窗，一開始全新安裝的話，使用預設設定即可，
以後若想選擇其他套件安裝還可以開啟這個視窗，預設安裝的話，
並不會下載很多套件，基本的安裝不會佔據很多容量，點擊下一步。

![](/img/2019-04-01_151735.png ':no-zoom')

會下載以下相依套件軟體，點擊下一步。

![](/img/2019-04-01_151856.png ':no-zoom')

開始安裝...

![](/img/2019-04-01_151925.png ':no-zoom')

點擊安裝完成

1.是否在桌面創建軟體自帶的終端機。

2.是否創建開始功能表項目。

![](/img/2019-04-01_152017.png ':no-zoom')

## 安裝 wget

執行剛剛的 setup-x86_64.exe，點擊下一步，到套件選擇的視窗。

tar (預設已安裝)

gawk (預設已安裝)

bzip2 (預設已安裝)

lynx (選擇安裝，以後會用到)

在搜尋框中輸入套件名稱，下拉選單中可以選擇版本。

![](/img/2019-04-01_154136.png ':no-zoom')

點擊下一步，會一併下載相依性檔案。

點擊下一步，然後完成安裝。

## 安裝 apt-cyg

上邊已經安裝過wget，其他的相依套件tar,gawk,bzip2

apt-cyg 安裝指令

```bash
[user@local ~]$ lynx -source rawgit.com/transcode-open/apt-cyg/master/apt-cyg > apt-cyg
[user@local ~]$ install apt-cyg /bin
```
或者是

```bash
# 將 apt-cyg 安裝到 /usr/local/bin
[user@local ~]$ wget rawgit.com/transcode-open/apt-cyg/master/apt-cyg -O /usr/local/bin/apt-cyg
[user@local ~]$ chmod +x /usr/local/bin/apt-cyg
```

列出常用 apt-cyg 指令

```bash
# 在已安裝的套件中搜尋與 dns 相關的套件
[user@local ~]$ apt-cyg search dns

# 線上搜尋(cygwin.com)與 dns 相關的套件
[user@local ~]$ apt-cyg searchall dns

# 安裝 bind-utils 套件
[user@local ~]$ apt-cyg install bind-utils

# 移除 bind-utils 套件
[user@local ~]$ apt-cyg remove bind-utils
```

## 更改 BASH 的顏色

BASH color prompt

```bash
# 編輯 bashrc
[user@local ~]$ vi /etc/bash.bashrc

# PS1 命令提示字串改好看
# 以下兩個設定選擇一個開啟
# export PS1='\[\033[1;33m\]\u\[\033[1;37m\]@\[\033[1;32m\]\h\[\033[1;37m\]:\[\033[1;31m\]\w \[\033[1;36m\]\$ \[\033[0m\]'
export PS1='\[\033[01;33m\]\u\[\033[00m\]@\[\033[01;32m\]\h\[\033[00m\]:[\[\033[01;31m\]\w\[\033[00m\]]\[\033[01;36m\]\$ \[\033[0m\]'

alias ll='ls -lh'
alias la='ls -lha'

# 讓 ls 和 grep 顯示有顏色
alias ls='ls -F -N --color=auto'
alias grep='grep --color=auto'
```

## 安裝 NodeJS 與 NPM
NodeJS官網 https://nodejs.org/en/download/

![](/img/2019-04-01_1834422.png)

下載安裝檔或者免安裝檔案，將其解壓縮到<b><font color="red">你指定</font></b>的路徑

路徑都可以隨你自己的意願

我這邊是：![](/img/2019-04-01_201101.png ':no-zoom')

`C:\Program Files\node-v10.15.3-win-x64`

並記好這個路徑，等一下會用到

將 NodeJS 路徑加到`$PATH`

```bash
# 將 NodeJS 路徑加到 PATH
[user@local ~]$ echo 'export PATH=$PATH":/cygdrive/c/Program Files/node-v10.15.3-win-x64"' >> ~/.bashrc

# 重整 bashrc，或者重開 terminal
[user@local ~]$ source ~/.bashrc

# 查詢 NodeJS 版本
[user@local ~]$ node -v
v10.15.3

# 查詢 npm 版本
[user@local ~]$ npm -v
6.4.1
```

## 安裝 Hyper Terminal
Hyper官網 https://hyper.is

解決 Hyper Terminal 中文疊字問題

```bash
# 修改 .hyper.js
# 找到並更改下列參數
termCSS: '.wc-node.unicode-node{width: 1em}'
```