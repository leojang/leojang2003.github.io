---
layout: post
title:  "C# Parallel For"
date:   2018-12-27 18:19:13 +0800
categories: jekyll update
---
{% highlight C# %}
        var lines = File.ReadAllLines("D:\\20180626CPSAU01.DAT");
        
        Parallel.For(0, lines.Length,
               index =>
               {
                 Interlocked.Add(ref totalSize, 1);
                 Console.WriteLine(totalSize);
                 Thread.Sleep(5000);
               });
{% endhighlight %}
