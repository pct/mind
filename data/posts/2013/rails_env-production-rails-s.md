RAILS_ENV=production rails s
======

##情境
明明 rails s 就可以測試 production 網站了，是這樣說的沒錯吧？

## 怎麼做？

1. 因為 `config/environments/production.rb` 檔案裡面有說 "Disable Rails's static asset server (Apache or nginx will already do this)"，所以把裡面的

	`config.serve_static_assets = false`

	改成

	`config.serve_static_assets = true`

2. 照常使用：

	`rake assets:precompile`

	`RAILS_ENV=production rails s`

3. 別忘記到有 apache/nginx 的 production 環境時把第一步驟改回來


## 結語

<del>我應該沒有誤人子弟，對吧？</del>