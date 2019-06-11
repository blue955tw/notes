## 前言

https://hexo.io/zh-tw/

必須先安裝好 ([安裝 NodeJS 與 NPM](cygwin/cygwin.md#安裝-nodejs-與-npm "安裝 NodeJS 與 NPM"))

## 安裝 Git

https://git-scm.com/

我這邊是下載免安裝版本 Git for Windows Setup -> 64-bit Git for Windows Setup

將 `git-bash` 加入右鍵

>1. Ctrl + R 執行 regedit.exe
>2. 找到 HKEY_CLASSES_ROOT\Directory\Background\shell (如果沒有shell機碼，可以新增一個)
>3. 在 shell 下新增機碼 Git Bush Here 這時你可以在右鍵會出現 "Git Bush Here" 選單
>4. 在 Git Bush Here 下新增 Icon 一個字串值，修改數值資料 \<你的 Git 路徑\>\mingw64\share\git\git-for-windows.ico
>5. 在 Git Bush Here 下新增 command 一個機碼，修改(預設值)數值 \<你的 Git 路徑\>\git-bash.exe

## 安裝 Hexo

https://hexo.io/zh-tw/docs/index.html

以下這個指令你可以使用CMD下去執行，不過必須先設定好 NodeJS 跟 NPM 的路徑。

你可以參考：[安裝 NodeJS 與 NPM](cygwin/cygwin.md#安裝-nodejs-與-npm "安裝 NodeJS 與 NPM")

```bash
# 從 NPM 安裝專案
~$ npm install -g hexo-cli

# 查看 Hexo 版本
~$ hexo -v

# 出現以下訊息就可以算是安裝成功
hexo-cli: 2.0.0
os: Windows_NT 6.1.7601 win32 x64
http_parser: 2.8.0
node: 10.15.3
v8: 6.8.275.32-node.51
uv: 1.23.2
zlib: 1.2.11
ares: 1.15.0
modules: 64
nghttp2: 1.34.0
napi: 3
openssl: 1.1.0j
icu: 62.1
unicode: 11.0
cldr: 33.1
tz: 2018e
```

以下是用 git-bash 執行

一旦 Hexo 完成後，請執行下列指令，Hexo 會在指定資料夾中建立所有您需要的檔案。

```bash
# <folder>你指定的資料夾
~$ hexo init <folder>
~$ cd <folder>
~$ npm install
```

啟動 Hexo

```bash
# 產生靜態網頁
~$ hexo g

# 啟動自帶預覽網頁
~$ hexo s

# 進入 http://localhost:4000 就可以看到 Hexo 的呈現結果了
INFO  Start processing
INFO  Hexo is running at http://localhost:4000 . Press Ctrl+C to stop.
```