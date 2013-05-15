upgrade rails4 beta1 to rc1
======

###緣起
這還要什麼緣起？就是 rc1 出現所以就要升級到 rc1 啦

那還要寫這篇幹嘛？因為單純修改 Gemfile 後，rails s 會再起不能，所以記錄一下步驟。

###錯誤訊息

	gems/railties-4.0.0.rc1/lib/rails/application/configuration.rb:144:in `const_get': uninitialized constant ActionDispatch::Session::EncryptedCookieStore (NameError)
	
###How?
1. 把 Gemfile 裡面的 rails 相關 gem，由 4.0.0.beta1 全部改為 4.0.0.rc1

2. 把 config/initializers/session_store.rb 中的

		:encrypted_cookie_store
		
	換成
		
		:cookie_store

3. 重新 rails s 吧

###結語
還沒學會爬就想要飛，碰壁是應該的

###參考資料
[rails4.0.0.beta1 -> rails4.0.0.rc1 migration guide](http://qiita.com/items/6e19c246d608abd9795b)