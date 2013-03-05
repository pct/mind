在 Mac 中用 7zip 壓縮檔案，給 Windows 用戶時就免除亂碼問題
======

其實，善心的保哥已經在這篇文章 [在 Mac 電腦壓縮的 ZIP 檔案如何正確在 Windows 下解壓縮](http://blog.miniasp.com/post/2012/05/12/How-to-correct-unzip-Mac-format-ZIP-file-with-chinese-filename-in-Windows.aspx) 告訴我們如果在 windows 要如何解決收到 Mac 來的壓縮檔總是亂碼的問題。

不過我因為情況不同，所以角度是 Mac user 提供壓縮檔給 Windows user，其解決方法如下(這裡提供的 command line 解決方案，或自行尋找 7zip on mac)：

1. 安裝 7zip

		$ brew install p7zip

2. 直接用 7zip 壓縮檔案

		$ cd 你的檔案位置
		$ 7za a 你要的檔名
		
就這樣，把壓縮好的檔案直接傳給你的朋友試試看 :)

<del>就這樣，一篇廢文又產生了，我才不信已經用 homebrew 的人會需要看這種文章，看到標題就夠了；所以這篇只是給自己看的沒錯(蓋章)</del>