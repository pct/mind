FreeBSD binary update
======

###緣起
其實這篇是要講 `freebsd-update` 這個 command

因為沒看什麼文件，所以以下都是胡亂猜測，如果不小心害到人，就只能先說對不起。(當然歡迎大家指正)

<del>謎之聲：這樣的文件你也敢丟出來害人</del>

###怎麼用

同 RELEASE 版本的更新：
	
	# freebsd-update fetch
	# freebsd-update install
	# mergemaster -U
	# portmaster -afvG (我是用破大師進行 package 更新，可以改成 portupgrade -avf)
	# reboot
	
跨 RELEASE 版本的更新：

	# freebsd-update upgrade -r 9.1-RELEASE
	# freebsd-update install
	# portmaster -afvG (我是用破大師進行 package 更新，可以改成 portupgrade -avf)
	# reboot
	# freebsd-update install
	# mergemaster -U
	# reboot
	
###參考資料
[更新与升级 FreeBSD](http://www.freebsd.org/doc/zh_CN/books/handbook/updating-upgrading-freebsdupdate.html)