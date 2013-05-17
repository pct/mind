programming in coffeescript notes
======
###緣起
那天因為某人要買大師級的參考書，所以也去書局閒晃一下。很幸運地發現這本書，應該可以稍微補足我殘缺的 coffeescript 知識，當然荷包就失血了。

書名：[Programming in CoffeeScript (Developer's Library)](http://www.amazon.com/Programming-CoffeeScript-Developers-Library-Bates/dp/032182010X)

書封(取自 Amazon)：

![Programming in CoffeeScript (Developer's Library)](http://ecx.images-amazon.com/images/I/51egrMIEBNL.jpg)

不過我看的是對岸翻譯版：

書名：[CoffeeScript 程序設計](http://www.tenlong.com.tw/items/711530193X?item_id=537305)

書封，取自豆瓣：

![CoffeeScript 程序設計](http://img3.douban.com/lpic/s24642727.jpg)

###小筆記
####scope
範例1, 以下會輸出都是 6

	for x in [1..5]
		setTimeout ->
			console.log x
		, 1
		
範例2, 用了 do 後，會出現 1~5

	for x in [1..5]
		do (x) ->
			setTimeout ->
				console.log x
			, 1

為什麼會這樣？因為就是 scope。在範例1 `setTimeout` 等待的同時，我的電腦已經在這等待時間內執行完 1~5 了。建議直接看編譯成 js 的後的結果就知道了。

####super
嗯，好用，要小心用 ;)

####Cake 與 Cakefile
範例(Cakefile)：

	option '-n', '--name [NAME]', 'name you want to say hello'
	task "hello", "Say hello to someone or say Hello, World", (option) ->
		if option.name?		
			console.log "Hello, #{option.name}"
		else
			console.log "Hello, World"
				
		
然後在 console 分別執行 `cake` 與 `cake hello`, `cake -n pct hello` 看結果

####Jasmine
書中提到的是 ruby gem, 不過我找到 [jasmine-node](https://github.com/mhevery/jasmine-node)，所以直接 

	npm install -g jasmine-node

###結語
這本書快看完了，可以準備送給大家了 :D

###後記
這本書已經被 Williams 預定了 :)