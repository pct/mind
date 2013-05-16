Rails custom form label name with auto input focus
======

###前言
這種怪怪的英文描述也只有我寫得出來

###緣起
身為台灣開發者，form label 用中文顯示也是正常。但 rails g scaffold 幫忙 gen 好的 code 就不會讓你點了 label 後就自動 focus 到該 label 指定的 input

###解法
很簡單，這跟 rails form 沒有關係，這是 label for 設定好就好的，所以範例如下，重點在`:for => '<前綴字>_id_num'`：

	<div class="control-group">
	  <%= f.label "身份證字號/居留證號", :class => 'control-label', :for => '<前綴字>_id_num' %>
	  <div class="controls">
	    <%= f.text_field :id_num, :class => 'text_field span3' %>
	  </div>
	</div>
	
###結語
這麼簡單也要 PO 文？沒錯，假裝一下這 blog 很豐富。

實際上卻也沒幾個人路過。