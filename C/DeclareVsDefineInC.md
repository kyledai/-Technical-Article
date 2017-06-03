「C」Declare vs Define in C
自己讀書有感，所以做了一下資料
相較於FB似乎比較適合放在這邊

主要是難以發現的全域變數未宣告初始值時
若你在Makefile又未加上-fno-common
會Default為Weak型態，各種同名Weak型態會共用同一地址。

<img src="http://image-store.slidesharecdn.com/8b556599-7da9-4d17-8833-fd88919502d2-original.png" width="640"/><BR>
