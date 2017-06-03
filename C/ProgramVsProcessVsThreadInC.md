「C」<BR>
說一下，Program, Process, Thread差別<BR>
之前也聽過好幾百次，不過那時對Program Load到Dram執行或CPU怎麼跑都沒有概念。<BR>
看太多反而搞混。所以這次打算以自己的話說一遍。盡量撇開，OS相關的。<BR>
<BR>
Program：死的Process，就是一個程式碼檔案，可能是一段Code，一個Bin。<BR>
<BR>
Process：Program執行後的樣子，一個Program連開十次，就會有10個Process一直在跑。（一個Process通常會由Cpu運行，如下圖）<BR>
<BR>
Thread：傳統的Process可看成只有一個Thread，但是如果想讓程式可以變輸入、邊做計算，就需要兩個Thread，多工的概念，<BR>
可以說是程式執行的最小單位。（下圖是在同一個Process裡有三個Thread在對記憶體做讀存）<BR>
<BR>
同Process不同Thread<BR>
共享：Heap, global variable <BR>
不共享：stack<BR>
<BR>
圖片來源：http://blog.marksylee.com/<BR>
<BR>
<img src="http://image-store.slidesharecdn.com/43e0372d-1c80-4dc0-a275-53edd30a9cb6-original.png" width="640"/><BR>
