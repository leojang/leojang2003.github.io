---
layout: post
title:  "C# Parallel For"
date:   2018-12-28 10:14:13 +0800
categories: C#
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

以下是 Parallel.cs 的原始碼
參考來源https://github.com/Microsoft/referencesource/blob/master/mscorlib/system/threading/Tasks/Parallel.cs
Parallel.cs 檔包含一個類別 ParallelOptions
{% highlight C# %}

    /// <summary>
    /// 設定 Parallel 方法執行時的選項
    /// </summary>    
    public class ParallelOptions
    {
        private TaskScheduler m_scheduler;
        private int m_maxDegreeOfParallelism;
        private CancellationToken m_cancellationToken;

        /// <summary>
        /// 初始化ParallelOptions類別
        /// </summary>                
        /// MaxDegreeOfParallelism 設成 -1, 設定平行數無上限
        /// CancellationToken 設成 non-cancelable token
        /// TaskScheduler 設成 default scheduler (TaskScheduler.Default)
        public ParallelOptions()
        {
            m_scheduler = TaskScheduler.Default;
            m_maxDegreeOfParallelism = -1;
            m_cancellationToken = CancellationToken.None;
        }
        
        public TaskScheduler TaskScheduler
        {
            get { return m_scheduler; }
            set { m_scheduler = value; }
        }

        // Convenience property used by TPL logic
        internal TaskScheduler EffectiveTaskScheduler
        {
            get
            {
                if (m_scheduler == null) return TaskScheduler.Current;
                else return m_scheduler;
            }
        }
        
        public int MaxDegreeOfParallelism
        {
            get { return m_maxDegreeOfParallelism; }
            set
            {
                if ((value == 0) || (value < -1))
                    throw new ArgumentOutOfRangeException("MaxDegreeOfParallelism");
                m_maxDegreeOfParallelism = value;
            }
        }

        /// Providing a CancellationToken
        /// to a Parallel method enables the operation to be
        /// exited early. Code external to the operation may cancel the token, and if the operation observes the
        /// token being set, it may exit early by throwing an
        public CancellationToken CancellationToken
        {
            get { return m_cancellationToken; }
            set
            {
                if (value == null)
                    throw new ArgumentNullException("CancellationToken");
                m_cancellationToken = value;
            }
        }

        internal int EffectiveMaxConcurrencyLevel
        {
            get
            {
                int rval = MaxDegreeOfParallelism;
                int schedulerMax = EffectiveTaskScheduler.MaximumConcurrencyLevel;
                if ((schedulerMax > 0) && (schedulerMax != Int32.MaxValue))
                {
                    rval = (rval == -1) ? schedulerMax : Math.Min(schedulerMax, rval);
                }
                return rval;
            }
        }
    }                

{% endhighlight %}
