#Game05

##題目敘述

有一個 Windows 7 的硬碟檔案，在某一路徑中有疑問的檔案（如附件），請找出 Flag

##解題方式

先用 `file` 看 `x.dll` 是什麼檔案，後發現是一個 `rar` 壓縮檔，並帶有註解說明解壓縮密碼是該 Windows 7 管理者的密碼 hash ，所以就使用 `bkhive` 以及 `samdump2` 。

先將 `C:\WINDOWS\System32\config\SAM` 以及 `C:\WINDOWS\System32\config\system` 取出

使用

```
bkhive system key
samdump2 SAM key
```

就可以顯示出管理者密碼的 hash 值，解開壓縮檔即為 Flag

##TODO

補上 `system` 以及 `SAM`
