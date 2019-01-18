---
layout: post
title:  "Insertion Sort"
date:   2018-10-09 00:43:13 +0800
categories: Computer-Science
tags: Algorithm

---
{% highlight C# %}
        public static void InsertionSort(int[] input)
        {
            for(int i = 1; i < input.Length; i++)
            {
                var key = input[i];
                var targetIndex = i - 1;
                while(targetIndex >= 0 && input[targetIndex] > key)
                {
                    input[targetIndex+1] = input[targetIndex];
                    input[targetIndex] = key;
                    targetIndex--;
                }
            }
        }
{% endhighlight %}

