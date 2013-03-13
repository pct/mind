rails sqlite3 to mysql migration
======

##情境
就是資料庫從 sqlite3 轉成使用 mysql。因為目前資料庫內容還算簡單，所以可以這樣作

## 步驟
1. 修改 `Gemfile`，加入：

	`gem 'mysql2'`

	`gem 'yaml_db'`
	
2. bundle 一下，安裝剛剛那兩個 gem：

	`$ bundle`
	
3. 備份一下你的 db 設定檔

	`$ cp config/database.yml config/database.yml.sqlite3`

4. 把 DB 資料 dump 出來

	`$ rake db:dump`
	
5. 改一下 `config/database.yml`，把 `sqlite3` 換成 `mysql2`

6. 到 mysql 建資料庫

	`rake db:setup`
	
	`rake db:schema:load`
	
7. 把剛剛 `db:dump` 結果再 `load` 回去

	`rake db:load`


## 參考資料 
1. [Convert a Ruby on Rails app from sqlite to MySQL?](http://stackoverflow.com/questions/1670154/convert-a-ruby-on-rails-app-from-sqlite-to-mysql)

## 結語
<del>不免俗又是廢文一篇，其實 google 就會幫你找到解答了，對吧？</del>