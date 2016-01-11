#Game11

##題目敘述

◎ 題目：
攻擊者針對無線網路進行側錄，欲竊取受害者登入104人力網站之帳號密碼(Flag)，請根據封包內容找到Flag。

◎ 提示：
你會取得含有兩個檔案，分別為1個以密碼壓縮過.zip檔，以及1個含有解壓縮密碼的.bmp，須先取得解壓縮密碼，解壓縮後取得pcap檔進行分析

◎ 附件： [Wep-Crack.rar]() [ImageHide.bmp]()

##解題思路

先使用 `ImageHide.exe` 將 `ImageHide.bmp` 中的資訊取出，並發現開資訊用 ROT13 編碼，解譯後即得到 `Wep-Crack.rar` 的解壓縮密碼

然後會得到使用 Wep 的 wifi 攔截封包，使用 aircrack-ng 將其中 wep 密碼解出，在使用 Wireshark 將 Wep 密碼輸入，將加密封包解密後，把用 filter 將 HTTP 封包取出，直接尋找 `password` 相關關鍵字，緊接在 `password` 之後的即為 flag

##TODO

補上 `Wep-Crack.rar` 以及 `ImageHide.bmp`