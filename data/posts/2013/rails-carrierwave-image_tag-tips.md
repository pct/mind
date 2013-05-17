rails carrierwave image_tag tips
======
###緣起
因為連抄都抄錯，所以才要筆記一下。

Carrierwave 的 gem [在這裡](https://github.com/carrierwaveuploader/carrierwave)。

###簡易有無圖片的判斷
有時候圖片上傳並非必要，所以後端要 show 照片時，範例寫著：

	<%= image_tag(@user.avatar_url) if @user.avatar? %>

亦即，我忘記 if @user.avatar? 後面的 `?`

忘記加 `?` 會發生什麼事？就是如果沒那張圖，那麼 rails 在 render 該 view 時就會報錯：500 Internal Server Error

###結語
用 rails 當然要懂一下 ruby，要不一定會有些細節容易出包的 Orz...
