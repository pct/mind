FreeBSD Passenger 4.0.5 Cannot execute bash
======

###前言
原本用 Passenger 3.0.19 好好的，手癢更新 FreeBSD server, 卻遇到了這樣的訊息：

    [ 2013-06-02 11:29:04.7868 23043/0x802060c00 Pool2/Spawner.h:159 ]: [App 23054 stderr] Cannot execute "bash": No such file or directory (errno=2)
    terminate called after throwing an instance of 'std::bad_cast'

###暫時解法
查資料發現這篇 [Passenger 4.0.4/4.0.5 - Cannot execute "bash"](https://groups.google.com/forum/?fromgroups#!topic/phusion-passenger/u0QN_F09UpI)

於是直接用比較不好的解法：

    sudo ln -s /usr/local/bin/bash /bin/bash

###結語

好心的 port maintainer, 會不會解決這個 issue 呢？

前提是，該來 send-pr 先？
