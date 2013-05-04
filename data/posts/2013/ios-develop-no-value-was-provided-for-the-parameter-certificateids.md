"No value was provided for the parameter certificateIds"
======

對啦，會遇到這種事真的很奇怪，按下 renew 是沒有反應的，會出現 這樣的 alert：

    No value was provided for the parameter certificateIds

![](http://mind.deep.tw/images/foo/renew_fail.png)

那麼，解決方式呢？

讓我們看看 [高手的回答](http://stackoverflow.com/questions/12253618/error-when-clicking-renew-for-ios-certificates)，就是要你去 [這邊](https://developer.apple.com/devcenter/ios/index.action) 更新一下 provisioning profile

但是說來也怪，在過期的項目點了 `Modify` 按鈕進去按下 `submit` 按鈕也沒用，所以我就猜到一定是 apple 設計的表單太聰明，一定要變更一下 form 表單再變更回來，就可以按下 `submit` 按鈕，去更新 provisioning profile 啦！

然後就可以進 Xcode 的 Organizer 去按下那 `Refresh` 按鈕，那麼，就順利可以看到以下的結果：

![](http://mind.deep.tw/images/foo/renew_success.png)

<del>那麼，看似沒用的筆記文，咱們下次見！</del>
