rails CSRF notes
======

### 起源

在一個案子中，需要讓 user 不需「登入」就可以執行 post。然後不小心用 curl post 居然也可以寫入，實在令人驚訝！

### 環境
rails 3.2.13

### 發現

我們使用 ajax post 的方式來讓 user 貼文，不過這不是重點，重點是你的 post，不管是 ajax post, 一般 form post，或你遠端 curl post，你都可以發現你的 rails log 寫著：

	WARNING: Can't verify CSRF token authenticity

BUT，這人生中最常出現的 BUT，會告訴你：

	Completed 201 Created in 50ms (Views: 4.6ms | ActiveRecord: 1.6ms)

驚！！！
	
	也就是你以為 rails 幫你擋下 CSRF，結果根本還是被寫入了

### 為什麼？

因為…讓我們來看連結：

1. [有人有相同情形](http://stackoverflow.com/questions/7203304/warning-cant-verify-csrf-token-authenticity-rails?rq=1)
2. [所以解法在這裡](http://stackoverflow.com/questions/5000333/how-does-rails-csrf-protection-work)
3. [為什麼會這樣](http://api.rubyonrails.org/classes/ActionController/RequestForgeryProtection.html#method-i-handle_unverified_request)

白話翻譯：

1. rails 的 CSRF 保護機制幫你判斷了非 GET 的操作但又沒提供 token，所以跟你說了：

		WARNING: Can't verify CSRF token authenticity
	

2. rails 在沒有「登入」的狀況下，也沒幫你阻止，因為他預設的 `handle_unverified_request` 就只幫你做了 `reset_session`

3. 你沒有使用 session 機制, 你 reset session 根本阻止不了 CSRF，所以資料就這樣被警告一下，還是被寫入

4. 你該怎麼辦？就直接在 ApplicationController 增加 `handle_unverified_request` 的 method, 自己判斷沒有 csrf-token 時該怎麼做吧

### 結語
rails 很不安全，大家不要用？才不是，是因為我是初學者，這些眉眉角角都要自己學；相信強者大大們早就知道這些事了，所以這篇又是廢文了。

那麼，廢文，咱們下篇見！ 

P.S. 因為是初學者，請各位大大們不吝指正，謝謝！
