---
layout: post
title:  "TaskFactory StartNew 研究"
date:   2018-12-28 11:25:00 +0800
categories: C#
---

TaskFactory.StartNew 有許多方法如下
[TaskFactory.StartNew Method](https://docs.microsoft.com/en-us/dotnet/api/system.threading.tasks.taskfactory.startnew?view=netframework-4.7.2#System_Threading_Tasks_TaskFactory_StartNew_System_Action_System_Object__System_Object_System_Threading_CancellationToken_System_Threading_Tasks_TaskCreationOptions_System_Threading_Tasks_TaskScheduler_).
這其中有用到許多的類別
CancellationToken Struct
{% highlight C# %}
[System.Runtime.InteropServices.ComVisible(false)]
public struct CancellationToken
{% endhighlight %}

