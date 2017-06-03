「HDCP」<BR>
端午節連假，這週跟HDMi、DP Team串高清影像的TRX。理解的一些HDCP的東西。<BR>
<BR>
（High-Bandwidth Digital Content Protection），是由英特爾公司所發展，主要是保護影像內容不被盜錄。<BR>
<BR>
在此介紹HDCP2.2，主要支持UHD也就是4K60以上傳輸，如果傳輸路徑中（如下圖），有一段沒有HDCP2.2的驗證，<BR>
Decoder就會回傳1.x的驗證，影片會降規格輸出480p之類。<BR>
線材：HDMI2.0、DP1.3以上<BR>
片源：Netflix、Youtube、顯卡、PS4 pro(可關閉）<BR>
<BR>
技術性的部分<BR>
1.直接的一組HDCP Key，直接讀直接用。<BR>
2.一把hdcp 2.2 encryption的Key，這個還需要一個對應的ASE Key來解（通常產品會以這種做法）。<BR>
解完之後就會變成1.那種可用的Key存在EEPROM 或Flash，就不需每次開機再存一次。<BR>
<BR>
這些HDCP Key需花錢像Intel 購買的也禁止外流<BR>
<BR>
圖片來源：http://en.tab-tv.com/<BR>
<img src="http://image-store.slidesharecdn.com/847b741b-4abf-452a-9a67-ff99d9fb34ee-original.jpeg" width="640"/><BR>
