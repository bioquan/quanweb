---
layout: post
title: 关于python中re模块split方法的使用
tags:  [python]
categories: [python]
author: XuQuan
excerpt: "关于python中re模块split方法的使用"
---

今天在写一段小代码的时候需要用到re.split()方法，在使用的过程中发现了一个以前不知道的新用法，发现这个用法还是挺实用的，就把它记录下来：

    >>> m = re.split( ‘\d+’ , ’dkjj23jjjj44’)
    >>>m
    [‘dkjj’ , ‘jjjj’ , ‘’ ]
    >>> m = re.split( ‘(\d+)’ , ’dkjj23jjjj44’)             #匹配部分加上（）
    >>>m
    [‘dkjj’ , ‘23’ , ‘jjjj’ , ‘44’ , ‘’ ]
    >>> m = re.split( ‘\d+’ , ’dkjj23jjjj44as’)            #匹配部分加上了（）
    >>>m
    [‘dkjj’ , ‘jjjj’ , ‘as’ ]
    >>> m = re.split( ‘(\d+)’ , ’dkjj23jjjj44as’)
    >>>m
    [‘dkjj’ , ‘23’ , ‘jjjj’ , ‘44’ , ‘as’ ]

在匹配部分加上（）之后所切出的结果是不同的，没有（）的没有保留所匹配的项，但是有（）的却能够保留了匹配的项，这个在某些需要保留匹配部分的使用过程是非常重要的。
