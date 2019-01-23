---
layout: post
title:  "Insertion Sort"
date:   2019-01-24 00:43:13 +0800
categories: Computer-Science
tags: Algorithm

---

Insertion sort pseudo code looks like this

{% highlight C# %}
//mark first element as sorted

//for each unsorted element X

//  'extract' the element X

//  for j = lastSortedIndex down to 0

//    if current element j > X

//      move sorted element to the right by 1

//    break loop and insert X here
{% endhighlight %}


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

