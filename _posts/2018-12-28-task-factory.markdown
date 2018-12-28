---
layout: post
title:  "TaskFactory 研究"
date:   2018-12-28 11:25:00 +0800
categories: C#
---
請參考 
https://docs.microsoft.com/en-us/dotnet/api/system.threading.tasks.taskfactory?view=netframework-4.7.2.
https://github.com/Microsoft/referencesource/blob/master/Microsoft.Bcl/System.Threading.Tasks.v1.5/System/Threading/Tasks/TaskFactory.cs
https://blog.darkthread.net/blog/net4-task/

TaskFactory.StartNew
{% highlight C# %}
public System.Threading.Tasks.Task StartNew (Action<object> action, object state, System.Threading.CancellationToken cancellationToken, System.Threading.Tasks.TaskCreationOptions creationOptions, System.Threading.Tasks.TaskScheduler scheduler);        
{% endhighlight %}

