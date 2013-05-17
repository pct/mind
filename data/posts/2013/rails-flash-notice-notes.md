rails flash notice notes
======
###緣起
在寫 rails form 的時候，做個成功、失敗的頁面。

###How?
####Controller
在你想要中斷流程，redirect 到 result 頁面時(當然，有 result 這個 action)：

	format.html {
		redirect_to :action => 'result'
		flash[:notice] = '要顯示的訊息'
	}
	
####View

	<% if flash[:notice] %><%= notice %><% end %>

###結語
是的，小東西也記錄一下 :)