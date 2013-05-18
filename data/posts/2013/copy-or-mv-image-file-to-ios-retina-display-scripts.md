copy or mv image file to ios retina display scripts
======
###前言
瑣碎的事情總是太多。

廢話不多說，直接切入正題。

###情境
你自己找了一堆圖檔，但是圖檔名稱都沒有 @2x，你需要用 command line 快速複製一份 @2x 或更改檔名

###script

更改檔名：

	$ ls |cut -d '.' -f 1|awk '{print "mv "$1".png "$1"@2x.png"}'|sh
	
複製成 @2x：

	$ ls |cut -d '.' -f 1|awk '{print "cp "$1".png "$1"@2x.png"}'|sh
	
###說實話
你沒事要去哪裡找一堆圖檔？

用 [這個 python script](https://github.com/odyniec/font-awesome-to-png) 幫你把所有 fontawesome 的字，轉成你指定大小的圖檔吧。

(先下載 fontawesome 的字型才有用喔)

比如你要黑色的圖：

	$ ./font-awesome-to-png.py --color '#111' --size 80 ALL

###結語
就這樣，要不沒事幹嘛改檔名呢？