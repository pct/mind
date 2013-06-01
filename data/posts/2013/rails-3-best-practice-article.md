rails 3 best practice article
======

偶然間在臉書找技術文，發現這個連結：

[rails-style-guide](https://github.com/JuanitoFatas/rails-style-guide/blob/master/README-zhTW.md)

其原文版：
[rails-style-guide](https://github.com/bbatsov/rails-style-guide)

一時間可能沒有辦法完全看完。

###節錄一些推薦的 gem 如下：

* [active_admin](https://github.com/gregbell/active_admin) - 有了 ActiveAdmin，創建 Rails 應用的管理介面就像兒戲。你會有一個很好的儀錶盤，圖形化 CRUD 介面以及更多東西。非常靈活且可客製化。
* [better_errors](https://github.com/charliesome/better_errors) - Better Errors 用更好更有效的錯誤頁面，取代了 Rails 標準的錯誤頁面。不僅可用在 Rails，任何將 Rack 當作中介軟體的 app 都可使用。
* [bullet](https://github.com/flyerhzm/bullet) - Bullet 就是為了幫助提昇應用的效能（藉由減少查詢）而打造的 gem。會在你開發應用時，替你注意你的查詢，並在需要 eager loading (N+1 查詢)時、或你在不必要的情況使用 eager loading 時，或是在應該要使用 counter cache 時，都會提醒你。
* [cancan](https://github.com/ryanb/cancan) - CanCan 是一個權限管理的 gem，
讓你可以管制用戶可存取的支援。所有的授權都定義在一個檔案裡（ability.rb），並提供許多方便的方法，讓你檢查及確保整個應用內權限是否是可得的。
* [capybara](https://github.com/jnicklas/capybara) - Capybara 旨在簡化整合測試 Rack 應用的過程，像是 Rails、Sinatra 或 Merb。 Capybara 模擬了真實用戶使用 web 應用的互動。它與你測試在運行的驅動無關，並原生搭載 Rack::Test 及 Selenium 支持。透過外部 gem 支持 HtmlUnit、WebKit 及 env.js 。與 RSpec & Cucumber 一起使用時工作良好。
* [carrierwave](https://github.com/jnicklas/carrierwave) - Rails 最後一個文件上傳解決方案。支持上傳檔案（及很多其它的酷玩意的）的本機儲存與雲端儲存。圖片後處理與 ImageMagick 整合得非常好。
* [client_side_validations](https://github.com/bcardarella/client_side_validations) -
  一個美妙的 gem，替你從現有的服務器端模型驗證自動產生 Javascript 用戶端驗證。高度推薦！
* [compass-rails](https://github.com/chriseppstein/compass) - 一個優秀的 gem，添加了某些 css 框架的支持。包括了 sass mixin 的蒐集，讓你減少 css 文件的程式碼並幫你解決瀏覽器相容問題。
* [cucumber-rails](https://github.com/cucumber/cucumber-rails) - Cucumber 是一個由 Ruby 所寫，開發功能測試的頂級工具。 cucumber-rails 提供了 Cucumber 的 Rails 整合。
* [devise](https://github.com/plataformatec/devise) - Devise 是 Rails 應用的一個完整解決方案。多數情況偏好使用 devise 來開始你的客制驗證方案。
* [fabrication](http://fabricationgem.org/) - 一個很好的假資料產生器（編輯者的選擇）。
* [factory_girl](https://github.com/thoughtbot/factory_girl) - 另一個 Fabrication 的選擇。一個成熟的假資料產生器。 Fabrication 的精神領袖先驅。
* [ffaker](https://github.com/EmmanuelOga/ffaker) - 實用的 gem 來產生仿造的資料（名字、地址，等等）。
* [feedzirra](https://github.com/pauldix/feedzirra) - 非常快速及靈活的 RSS 或 Atom 種子解析器。
* [friendly_id](https://github.com/norman/friendly_id) - 透過使用某些具描述性的模型屬性，而不是使用 id，允許你創建人類可讀的網址。
* [globalize3](https://github.com/svenfuchs/globalize3.git) - Globalize3 是 Globalize Gem 的後繼者，針對 ActiveRecord 3.x 設計。基於新的 I18n API 打造而成，並幫 ActiveRecord 模型新增了事務功能。
* [guard](https://github.com/guard/guard) - 極佳的 gem 監控文件變化及任務的調用。搭載了很多實用的擴充。遠優於 autotest 與 [watchr](https://github.com/mynyml/watchr)。
* [haml-rails](https://github.com/indirect/haml-rails) - haml-rails 提供了 Haml 的 Rails 整合。
* [haml](http://haml-lang.com) - Haml 是一個簡潔的模型語言，被很多人認為（包括我）遠優於Erb。
* [kaminari](https://github.com/amatsuda/kaminari) - 很棒的分頁解決方案。
* [machinist](https://github.com/notahat/machinist) - 假資料不好玩，Machinist 才好玩。
* [rspec-rails](https://github.com/rspec/rspec-rails) - RSpec 是 Test::MiniTest 的取代者。我不高度推薦 RSpec。 rspec-rails 提供了 RSpec 的 Rails 整合。
* [simple_form](https://github.com/plataformatec/simple_form) - 一旦用過 simple_form（或 formatastic），你就不想聽到關於 Rails 預設的表單。它是一個創造表單很棒的 DSL。
* [simplecov-rcov](https://github.com/fguillen/simplecov-rcov) - 為了 SimpleCov 打造的 RCov formatter。若你想使用 SimpleCov 搭配 Hudson 持續整合服務器，很有用。
* [simplecov](https://github.com/colszowka/simplecov) - 程式碼覆蓋率工具。不像 RCov，完全相容 Ruby 1.9。產生精美的報告。必須用！
* [slim](http://slim-lang.com) - Slim 是一個簡潔的模版語言，被視為是遠遠優於 HAML(Erb 就更不用說了)的語言。唯一會阻止我大規模地使用它的是，主流 IDE 及編輯器對它的支持不好。但它的效能是非凡的。
* [spork](https://github.com/sporkrb/spork) - 一個給測試框架（RSpec 或現今 Cucumber）用的 DRb 服務器，每次運行前確保分支出一個乾淨的測試狀態。簡單的說，預載很多測試環境的結果是大幅降低你的測試啟動時間，絕對必須用！
* [sunspot](https://github.com/sunspot/sunspot) - 基於 SOLR 的全文檢索引擎。

* [foreman](https://github.com/ddollar/foreman) - 若你的專案依賴各種外部的進程使用 foreman 來管理它們。

### 其他推薦閱讀

* [The Rails 3 Way](http://www.amazon.com/Rails-Way-Addison-Wesley-Professional-Ruby/dp/0321601661)
* [Ruby on Rails Guides](http://guides.rubyonrails.org/)
* [The RSpec Book](http://pragprog.com/book/achbd/the-rspec-book)
* [The Cucumber Book](http://pragprog.com/book/hwcuc/the-cucumber-book)
* [Everyday Rails Testing with RSpec](https://leanpub.com/everydayrailsrspec) 