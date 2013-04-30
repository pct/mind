rails carrierwave image format error
======

### 緣起

在使用 carrierwave 時，在 Mac 沒問題，但在 production server 上傳圖片(.png)就失敗，而且錯誤訊息是：

	No decode delegate for this image format.

### 環境
已經安裝 imagemagick
	
### 資料查找

http://stackoverflow.com/questions/13023700/rmagick-fails-to-manipulate-png

### 重點
使用以下指令查找 imagemagick 支援的 format：

	identify -list format
	
發現沒有 PNG，所以在系統裝一下 libpng，解決！
(看要不要順便裝 libjpeg, jasper…，裝好 library 後還是不行，就重裝 imagemagick 吧)

### 結語
人太弱就會到處碰壁，又差人家一截了(泣)
