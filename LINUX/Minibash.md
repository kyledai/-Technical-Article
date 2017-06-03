「LINUX」簡單呼叫程式的minibash<BR>
在書上看到的覺得挺有趣，簡單的說他會呼叫fork()創立一行程，如果fork()成功會return一個pid就是常用LINUX會看到的pid，<BR>
最後呼叫execlp()去執行程式。（除了execlp（）以外還有很多種類似的function，execl()、execle()...之類的）<BR>
<BR>
然後他會自己呼叫sys_execve()進行一對參數檢查，然後呼叫do_execve()搜尋檔案，若然後他會先讀前128bit判斷是什麼檔，在呼叫對應的function。<BR>
<BR>
因為LINUX支援的執行檔不只一種<BR>
例如：<BR>
<BR>
ELF格式前4byte：0x7f、'e'、'l'、'f'<BR>
Java可執行檔格式前4byte：'c'、'a'、'f'、'e'<BR>
<BR>
腳本類：<BR>
Shell：#!/bin/sh、#!/bin/bash(通常default為sh)<BR>
Perl：#!/bin/perl<BR>
Python：#!/bin/python<BR>
<BR>
對應不同的格式會在呼叫不同的function去執行，所以寫腳本時，第一行會加以上的字去提醒。<BR>
<BR>
圖片來源：A Programmer Prepares<BR>
<BR>
<img src="http://image-store.slidesharecdn.com/3b298f4e-bbc5-426f-ad2b-2f9755555d30-original.jpeg" width="640"/><BR>
