FreeBSD rbenv install ruby 2.0
======

因為，所以。

FreeBSD 10.0-CURRENT 已經是用 clang 而非 gcc，所以在 rbenv 找不到 gcc 的情況下，只要這樣：

	CC=/usr/bin/clang rbenv-install 2.0.0-p247
	
解決。

參考來源(對方是在 Mac 環境下遇到)：[http://accretiondisc.com/blog/2012/08/20/more-rbenv-notes/](http://accretiondisc.com/blog/2012/08/20/more-rbenv-notes/)

所以這樣廢文又一篇了 :)