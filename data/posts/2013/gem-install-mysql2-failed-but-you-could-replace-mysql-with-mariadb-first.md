gem install mysql2 failed but you could replace mysql with mariadb first
======

###緣由

環境：Mac 10.7 and 10.8

欲安裝/更新 gem mysql2

###錯誤訊息

	Fetching: mysql2-0.3.13.gem (100%)
	Building native extensions.  This could take a while...
	ERROR:  Error installing mysql2:
		ERROR: Failed to build gem native extension.
	
	    /Users/pct/.rvm/rubies/ruby-2.0.0-p247/bin/ruby extconf.rb
	checking for rb_thread_blocking_region()... yes
	checking for rb_wait_for_single_fd()... yes
	checking for rb_hash_dup()... yes
	checking for rb_intern3()... yes
	checking for mysql.h... no
	checking for mysql/mysql.h... no
	-----
	mysql.h is missing.  please check your installation of mysql and try again.
	-----
	*** extconf.rb failed ***
	Could not create Makefile due to some reason, probably lack of necessary
	libraries and/or headers.  Check the mkmf.log file for more details.  You may
	need configuration options.
	
	Provided configuration options:
		--with-opt-dir
		--with-opt-include
		--without-opt-include=${opt-dir}/include
		--with-opt-lib
		--without-opt-lib=${opt-dir}/lib
		--with-make-prog
		--without-make-prog
		--srcdir=.
		--curdir
		--ruby=/Users/pct/.rvm/rubies/ruby-2.0.0-p247/bin/ruby
		--with-mysql-config
		--without-mysql-config

###偷懶解決方式

	$ brew remove mysql
	$ brew install mariadb
	$ gem install mysql2

###實際解決方式？
還沒測，但就趁機換 mariadb 了 :)