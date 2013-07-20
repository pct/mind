FreeBSD use clang when OSVERSION greater than 900033
======

###緣起

你知道 FreeBSD 的 www/node-devel 從 0.11.1 之後，就沒有更新了嘛？明明已經到 0.11.4 了說。

###發現

查找 Error log 說：

	../deps/v8/include/v8.h:6215: sorry, unimplemented: 
	inlining failed in call to 'v8::Handlev8::Primitive v8::Null(v8::Isolate*)': function not inlinable
	
然後 [https://github.com/joyent/node/issues/5568](https://github.com/joyent/node/issues/5568) 這篇給了靈感。

那不就是因為 FreeBSD 內建 GCC 還停留在 `gcc version 4.2.1 20070831 patched [FreeBSD]` 所造成？

###解決方式
看了其他的 ports，將以下判斷加進 Makefile，測試後果然 OK！

	.include <bsd.port.options.mk>

	.if ${OSVERSION} >= 900033 && exists(/usr/bin/clang)
	CC=     clang
	CXX=    clang++
	GYP_DEFINES+=   clang=1
	.else
	USE_GCC?=       4.6+
	GYP_DEFINES+=   gcc_version=${CXX:S/g++//}
	.endif
	
目前已經 send-pr 了，就看看 committer 看了這段有無要修改了。