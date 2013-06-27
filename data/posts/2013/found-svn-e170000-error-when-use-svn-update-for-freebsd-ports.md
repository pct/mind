Found svn E170000 error when use svn update for FreeBSD ports
======
其實，以前沒發生這情形的，是更新了 svn 1.8.0 後，發生以下的情形。

今天在更新 FreeBSD ports 的時候(改用 svn 的 ports)，出現了以下的 Error：

	svn: E170000: 無法辨識的 URL 綱要 'http://svn0.us-west.freebsd.org/ports/head'
	
查了 svn E170000 的 Error，其他人都說，就是 svn 認不得 http, https 這樣的網址，解決方式就是讓 svn 要認得。

那麼，其實很簡單，直接到 /usr/ports/devel/subversion 下 `make config`，把以下這個 module enable，重編  svn 就好了：

	[x] SERF              WebDAV/Delta-V (HTTP/HTTPS) repo access module
	
截圖如下：

![FreeBSD enable svn SERF module](https://raw.github.com/pct/mind/gh-pages/images/foo/svn-enable-serf-module.png)

而，其實我直接去 google 是比較不好的，因為後來才發現 /usr/ports/UPDATING 寫得好好的：

	20130619:
  		AFFECTS: users of devel/subversion
  		AUTHOR: ohauer@FreeBSD.org

  		devel/subversion has been upgraded from 1.7.10 to 1.8.0

  		If you want to upgrade, and use http/https access to repositories,
  		please check, that the SERF option is enabled, as NEON support
  		is gone. Also, mod_dontdothat and svnauthz_validate are
  		now eanbled with one option TOOLS, among other new tools
  		and SVNMUCC is enabled always.

  		subversion-1.7.x is available as devel/subversion17

  		To stay on subversion-1.7.x set in /etc/make.conf
  		WITH_SUBVERSION_VER=17
  		and use the following command

  		# pkg set -o devel/subversion:devel/subversion17

  		or

  		# portmaster -o devel/subversion17 devel/subversion