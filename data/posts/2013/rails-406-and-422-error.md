rails 406 and 422 error
======

###緣起
身為 rails 新手，常碰壁也是應該的

這是在處理前後端 route 不一致，且要客製前端 url + ajax post 時不小心撞的壁

<del>而且撞壁還要亂寫記錄來害別人</del>，實在不可取。所以請不小心路過的大大們幫忙指正，謝謝！

###HTTP 406 Not Acceptable?
會遇到這情形，是因為不管是 form_for 或 simple_form_for 如果沒有指定 json 格式的回傳，就會採用 html 回傳。

但是偏偏你已經拔除 render html 的相關 function，所以就報錯了。

因此，在 form_for 或 simple_form_for 指定 :url 到 json url 就好了

###422 Unprocessable Entity Error?
你已經 pass 了上述 406 那關，但是你又看到了 422 error，why？

先檢查一下你 post form 時，有無漏掉欄位、或是格式不對沒有被 server 驗證通過。

只要格式符合，應該就會正常 pass 了 :)

###結語
Web 技術學不完，繼續加油。