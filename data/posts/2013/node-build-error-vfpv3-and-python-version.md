node build error vfpv3 and python version
======

###前言
由於某年的 H4 聚會，發現了 node 跟 v8，所以那時就開始想把 node porting 到 FreeBSD 上。那時，是 node 版本還在 0.1 的年代…

人老的時候，總是會回顧一下年輕的時候做了什麼荒唐事，然後再回頭發現自己現在一事無成：

![FreeBSD NEW PORT www/node](https://raw.github.com/pct/mind/gh-pages/images/foo/freebsd-node-first-pr.png)

雖然這個 pr 也不是一次就過…

雖然，那時還有時間晚上去聚會…

但那都不是重點。

###沒事提什麼回顧？
是的，因為今天收到一封來自瑞典的信，地址是 Stockholm，亦即，斯德哥爾摩。

由於是 maintainer，收到 node build error 的信件也是正常的，對吧？

看到國外的高手們看似愜意的生活，我卻還沒有能力跟膽識可以去國外生活，所以只能在電腦前稍微感嘆一下。<del>我也絕對不會輕易說出口，很羨慕昨晚 Ruby Tuesday 24 的上台分享的、在日本工作的台灣工程師，可以舉家遷移到別的優秀國家，是很有能力的展現</del>

###真正重點

對方錯誤訊息如下：

	===>  Configuring for node-0.10.12
		File "./configure", line 441
		fpu = 'vfpv3' if armv7 else 'vfpv2'
		
###解決辦法：
1. 改 code [https://github.com/joyent/node/issues/4142](https://github.com/joyent/node/issues/4142)
2. [或改用正確版本的 python, 即 python2.7](http://stackoverflow.com/questions/14989164/node-js-configure-file-syntax-error-line-433)

###那人生的解決辦法呢？
我還在想。

不過也許哪天我可以帶心愛的老婆跟女兒出國度假、不用煩惱時，表示我已經找到一些辦法了。