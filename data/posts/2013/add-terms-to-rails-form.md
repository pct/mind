Add terms to rails form
======

###前言
因為還是嫩咖，所以邊作邊記錄下來，應該不是最佳解，但可以請有路過、看不過的人，幫忙糾正。

###緣起
在您平日的操作中，送出表單前，是不是都要勾取「我同意」「我已閱讀且同意...」那些約定呢？

###How?

情況一、原本就有考慮到這些事情，所以早就把 terms 建進資料庫，所以只要在 model 有：

	# terms
	attr_accessible :terms
	validates :terms, :presence => { :message => '不能為空'}
	validates_numericality_of :terms, :equal_to => 1,  :message => '需要同意活動聲明'
		

情況二、原本沒考慮，或是 terms 本來就不該是欄位，那也沒關係，只要在 model 加入

	# terms
	attr_accessor :terms #就是比上例多這行
	attr_accessible :terms
	validates :terms, :presence => { :message => '不能為空'}
	validates_numericality_of :terms, :equal_to => 1,  :message => '需要同意活動聲明'

然後，不管是情況一、二，在 form 裡面加入底下這行，就可以運作了！(不過 controller 當然本來就要 ready 好)

	<%= f.input :terms, as: :boolean, :label => "我已閱讀並同意遵守...之規定。" %>
	
###結語
一樣，人太廢所以需要邊學邊作，也需要各位幫忙指正了 :)