freebsd service command
======
今天一直重新編譯 mysql-server 看 mysql 編碼問題, 所以一直在 /usr/local/etc/rc.d/mysql-server restart

然後靈光一閃就想說，FreeBSD 應該會有對應於很多 Linux distro 都有的 `service` command 才對。

果不其然，查了一下，果然有！

下 `service` 後，出現：

	Usage:
	service -e
	service [-v] -l | -r
	service [-v] <rc.d script> start|stop|etc.
	service -h

	-e	Show services that are enabled
	-l	List all scripts in /etc/rc.d and /usr/local/etc/rc.d
	-r	Show the results of boot time rcorder
	-v	Verbose
	
也就是之後就可以 `service mysql-server restart` 就好啦。

網友 @Nephom 說「相信我，用完整路徑會比較好....因為....有些command會沒寫好」。我是相信的，因為很久以前我也遇過 cd /usr/local/etc/rc.d; ./apache2x start 但是卻 start 不起來的情況，但使用 /usr/local/etc/rc.d/apache2x start 卻又正常 :P 