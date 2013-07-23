FreeBSD rubygem passenger with rake nginx
======

###事由
最近在 FreeBSD 使用 rails4，遇到一點小問題。因為沒有使用 www/rubygem-passenger 而是自己用 gem install passenger，導致什麼找不到 watchdog 之類的 nginx 問題。

其實這也不限於 FreeBSD，而是 Linux 也要有，所以這是必備步驟？(如果不是使用一些幫你什麼都準備好的系統的話)

###解決方式
查找別人的心得，以及使用 www/rubygem-passenger 時，都有這個項目，就是：

	# cd `passenger-config --root`
	# rake nginx
	
不管是 FreeBSD or Linux，照做後就好了。

###然後就沒有其他問題了？
才不。

因為 passenger + nginx 實際 run 的時候，看來某些 code 是針對 Linux 寫的，所以才有 ls -v 這樣的 error：

	ERROR: cannot execute command 'lsof': errno=2
	Falling back to another mechanism for dumping file descriptors.
	ls: illegal option -- v
	usage: ls [-ABCFGHILPRSTUWZabcdfghiklmnopqrstuwx1] [-D format] [file ...]
	ERROR: Could not run 'ls' to dump file descriptor information!
	
以及，偶爾你也會遇到明明 FreeBSD 主機就有裝 bash, 但是 passenger 照樣報錯，說找不到 bash command。
此時，你也就先這樣解決： 

	# ln -s /usr/local/bin/bash /bin/bash
	
###既然問題那麼多(有嗎？)你怎不學大家用 Linux 就好？
原點。

我是為了 FreeBSD 才走岔路的，要不現在應該也是在某小報被長官壓迫寫一些自己不喜歡的文章來娛樂小眾吧。
