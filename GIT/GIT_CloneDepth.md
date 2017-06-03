「GIT」<BR>
最近在寫GIT的文章，不過之後因為工作需求要去使用SVN，人生就是這樣，哈哈<BR>
還是會繼續寫跟C跟GIT有關的文章。「今天提一下讓Clone速度變快的方法」。<BR>
<BR>
GIT Clone的Depth可以決定要Clone的Commit ID數量，下圖中的5代表只Clone前5個Commit ID。<BR>
可以大大的減少Clone的速度。但是檔案大小差不多(個人推測是會減少很多Clone小檔案的時間)<BR>
<BR>
另外Branch可以決定Clone下來的分支，可以與Depth連用決定Clone哪個Branch下的Commit ID。<BR>
<BR>
<img src="http://image-store.slidesharecdn.com/c37eea86-5391-41e9-a18b-b2a23fbb55dc-original.png" width="640"/><BR>
