FreeBSD vim lite build error undefined reference to libintl_gettext
======

###環境
FreeBSD 10.0-CURRENT

欲更新為 vim-7.3.1314

###疑問？
還是不曉得為什麼會發生這樣的事，<del>有空來研究一下</del>好了

	objects/buffer.o: In function `sign_list_placed': 
	buffer.c:(.text+0x368): undefined reference to `libintl_gettext' 
	buffer.c:(.text+0x3bd): undefined reference to `libintl_gettext' 
	buffer.c:(.text+0x415): undefined reference to `libintl_gettext' 
	
別人也有遇到相同的問題：[http://www.freebsd.org/cgi/query-pr.cgi?pr=168287](http://www.freebsd.org/cgi/query-pr.cgi?pr=168287)

###解法？
然後看到這篇 [http://www.mavetju.org/mail/view_message.php?list=freebsd-ports&id=3746713](http://www.mavetju.org/mail/view_message.php?list=freebsd-ports&id=3746713)

所以來 try 一下：

	  make -C /usr/ports/editors/vim-lite configure post-configure all
	  
確定 pass。

所以直接：

	  make -C /usr/ports/editors/vim configure post-configure install
	  
解決本次的問題。

但這顯然不是這樣解。

###研究？

實際取得 vim-7.3，不透過 ports 安裝，所以沒有 Makefile 的干擾，單純：

	$ ./configure && make
	
這樣也是 pass 的。

所以，<del>找時間</del>來 send-pr？應該問題就出在 ports patch 到不該 patch 的地方吧？




