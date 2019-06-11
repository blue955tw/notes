## 安裝 docsify

https://docsify.js.org/#/zh-cn/quickstart

安裝 docsify-cli (必須先安裝好 [安裝 NodeJS 與 NPM](cygwin/cygwin.md#安裝-nodejs-與-npm "安裝 NodeJS 與 NPM"))

```bash
~$ npm i docsify-cli -g
```
初始化項目 `./notes` 端看你的資料夾名稱，做適時修改。</br>
如果你已經初始化過了，不要再執行這個指令，會重新覆蓋你的 `index.html` `README.md` 檔案。

```bash
~$ docsify init ./notes
```

啟動預覽項目

```bash
~$ docsify serve ./notes
```

GIT
```bash
~$ git add .
~$ git commit -m "ok"
~$ git push
```