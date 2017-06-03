「GIT」<BR>
等早餐的時間說，GIT Reset-hard, mixed, soft。<BR>
圖是亂抓的。GIT儲存檔案的位置有三種。<BR>
Working Tree, Stage(Index), Repository<BR>
<BR>
GIT commit的過程<BR>
1.一般修改檔案是在Working Tree也叫Untracked檔<BR>
2.用Add將untracked檔案從Working Tree加到Stage<BR>
3.用Commit將Staged 的檔案Commit到Repository<BR>
<BR>
GIT reset的三種不同<BR>
1.Soft=>將Repository的部分還原<BR>
2.Mixed=>將Repository, Staged的部分還原<BR>
3.Hard=>將Repository, Staged, Working Tree的部分還原<BR>
<BR>
<img src="http://image-store.slidesharecdn.com/35c2b812-91a2-4e12-ae0c-e6063a612ff7-original.jpeg" width="640"/><BR>
