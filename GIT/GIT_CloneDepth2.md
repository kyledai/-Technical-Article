「GIT」<BR>
之前所述使用clone --depth加快clone 速度的指令<BR>
使用--depth參數，選擇Clone的commit ID數<BR>
提出一些其他小技巧<BR>
<BR>
1.使用--depth後，突然要把之前的history下載下來<BR>
可以使用pull --unshallow參數<BR>
<BR>
2.使用--depth，push到remote有conflict 的現象；<BR>
•可以正常使用pull --rebase來做rebase<BR>
•此時的pull也需決定其--depth。<BR>
•pull depth到的history，須同等於你一開始使用clone depth的history或更正之前。<BR>
