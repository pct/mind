FreeBSD mysql server charset utf8
======
###緣起

最近在更新某版本 mysql-server 的時候，發現編碼不對。那個 latin1 又出現了！

但我明明在 ports.conf 有加上

	WITH_CHARSET=utf8
	WITH_COLLATION=utf8_general_ci
	
不過編譯還是無效。

###發現

Google 後發現 [這篇](http://bbs.chinaunix.net/thread-3853083-1-1.html)，上面就說某版本的 mysql-server 自從改用 cmake 來編譯後，已無那些選項。所以重編再多次，或是 make 時使用 `-DWITH_CHARSET=utf8` 這種，是無效的。

###解決

雖然對岸作者 send-pr 不過沒有被該 port 的 maintainer 接受，所以就要在 server 改 Makefile

因為只是自己用，所以兩行就夠了：

	-DDEFAULT_CHARSET=utf8 \
	-DDEFAULT_COLLATION=utf8_general_ci
	
###my.cnf?

明明就如 maintainer 說的，只要修改 my.cnf 就好了，不是嗎？

但，聽說 <b>要在產生 /var/db/mysql 前要先設定好 my.cnf</b> 才行，如果真是這樣，那對我而言，這不是解決方案而是撞壁方案了…

###結尾
這種小事還要 Google, 我也真是技不如人啊 Orz...