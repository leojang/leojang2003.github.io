---
layout: post
title:  "CancellationToken 說明"
date:   2018-12-28 13:05:13 +0800
categories: C#
---
參考 [CancellationToken](https://docs.microsoft.com/en-us/dotnet/api/system.threading.cancellationtoken?view=netframework-4.7.2).
我們先產生一個 CancellationTokenSource 物件，CancellationTokenSource 物件會產生 cancellation token，CancellationTokenSource 傳至 TaskFactory 物件，TaskFactory 物件再將 cancellation token 傳至各 task。
{% highlight C# %}
        
{% endhighlight %}

