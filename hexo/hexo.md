## 前言

https://hexo.io/zh-tw/

必須先安裝好 [安裝 NodeJS 與 NPM](cygwin/cygwin.md#安裝-nodejs-與-npm)

## 安裝 Git

https://git-scm.com/

我這邊是下載免安裝版本 Git for Windows Setup --> 64-bit Git for Windows Setup

將 `git-bash` 加入右鍵

>1. Ctrl + R 執行 `regedit.exe`
>2. 找到 HKEY_CLASSES_ROOT\Directory\Background\shell（如果沒有shell機碼，可以新增一個）
>3. 在 shell 下新增機碼 `Git Bush Here` 這時你可以在右鍵會出現 "Git Bush Here" 選單
>4. 在 Git Bush Here 下新增 `Icon` 一個字串值，修改數值資料 `<Your Git Path>\mingw64\share\git\git-for-windows.ico`
>5. 在 Git Bush Here 下新增 `command` 一個機碼，修改(預設值)數值 `<Your Git Path>\git-bash.exe`

啟動預覽項目

```bash
~$ docsify serve ./docs
```

GIT
```bash
~$ git add .
~$ git commit -m "ok"
~$ git push
```