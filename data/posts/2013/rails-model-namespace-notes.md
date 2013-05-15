rails model namespace notes
======

###緣起
有時候做後台，使用 rails g scaffold 是可以很快速的，但，在前後台切分的架構，有時候也不是把後台的程式部分搬過來就可以滿足一切需求

###Error log?

	找不到 "books" 這個 table (看範例會知道這 table 不存在，存在的是 member_books)
	
###範例
後台：

	$ rails g scaffold member/books title:string
	
然後你想說就把產生的 member/books model copy 一份到前台，在來進行調整 <-- 這當然沒問題。

問題在於，有無 copy 完整。

今天遇到的初學者的錯誤就是沒 copy 完整，所以漏了 copy model/member.rb，這個檔案內容是：

	module Member
		def self.table_name_prefix
			'member_'
		end
	end
	
有了幫你設定 table name prefix 的檔案後，問題自然就迎刃而解了。

###參考資料
[Handling namespace models (classes) in namespace](http://stackoverflow.com/questions/5852626/handling-namespace-models-classes-in-namespace)

###結語
經驗是靠撞壁出來的 <-- 我是說我自己
