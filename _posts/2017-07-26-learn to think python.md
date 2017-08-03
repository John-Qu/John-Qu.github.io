---
layout: post
title:  "我学习用python思考"
date: 2017-08-02 17:14:16 +0800
categories: tools
---

这里是我读Allen B. Downey的[Think Python: How to Think Like a Computer Scientist](http://greenteapress.com/thinkpython2/html/index.html)作的复盘笔记，争取每天更新一章，估计四周读完第一遍。Mindnode的笔记还是原汁原味地贴图出来好看，最后我再导出Markdown格式，更新在这里。

## [整体图景](http://greenteapress.com/thinkpython2/html/index.html)

2017-07-26。

Wozniak[建议没有整体图景之前不要拼图](https://www.supermemo.com/en/articles/20rules)，这样效率相对低，我就把目录抄了一遍。果然感觉更舒服。

![整体图景](https://ws3.sinaimg.cn/large/006tNc79gy1fhyav1jf0wj31b80rkai0.jpg)

## [前言的话](http://greenteapress.com/thinkpython2/html/thinkpython2001.html)

2017-07-26.

![前言的话](https://ws3.sinaimg.cn/large/006tNc79gy1fhyavhc78mj317o0toq95.jpg)

## [程序语言](http://greenteapress.com/thinkpython2/html/thinkpython2002.html)

2017-07-26，这是对照原文写的，有过细之嫌。下次只写对自己有提示的地方就可以了。我不是做讲义，而是给自己做复盘。

![程序语言](https://ws1.sinaimg.cn/large/006tNc79gy1fhyaupgwkvj31701jyap7.jpg)

## [变量陈述](http://greenteapress.com/thinkpython2/html/thinkpython2003.html)

2017-07-27，这次几乎是背着写的，有主动回忆，感觉挺好。

![变量陈述](https://ws4.sinaimg.cn/large/006tNc79gy1fhyaud99ekj31h412ewoh.jpg)

## [函数](http://greenteapress.com/thinkpython2/html/thinkpython2004.html)

2017-07-28，今天学得不慢，做练习不太顺：E3我没有读清楚问题，自己给自己设定新任务：用一个参数控制打出多大的格子。但是这个功能如果不用循环语句，只用目前见过的命令，应该做不到。

![](https://ws3.sinaimg.cn/large/006tNc79gy1fhzoo3qq5mj30uc1lcar4.jpg)

## 4.  [案例：交互界面设计](http://greenteapress.com/thinkpython2/html/thinkpython2005.html)

- 2017-07-31，读课文，做内部例题。我Debug的方式太傻了，其实一眼就该看出来sin函数给了负数值。
- 2017-08-01，做复盘，做课后练习。还有两道联系题，螺线和字母表，都应该很有意思，今天来不及做了。


![](https://ws2.sinaimg.cn/large/006tNc79gy1fi4cs9k91tj31kw2m47wh.jpg)

## [条件和反复](http://greenteapress.com/thinkpython2/html/thinkpython2006.html#sec68)

2017-08-02，末两个练习用到上一章turtle的练习，今天没做，也留着。

![](https://ws2.sinaimg.cn/large/006tKfTcgy1fi5hzn7smij318e15ywol.jpg)

### 练习5.14-1：把以秒计的格林威治时间转为当前时间。

上午做了一小时，午饭后跑出来了。又写第二版，用recurse。

第一版：

```python
import time
greenwich = time.time()

hash_one_year = 86400 * 365
hash_years = greenwich // hash_one_year

def that_year(n):
    """Calculate that nth year after 1970 has how many seconds

        n: the nth year after 1970
    """
    y = 1970 + n
    if (y % 4) == 0:
        that_year = 366 * 86400
    else:
        that_year = 365 * 86400
    return that_year


year_remain = greenwich
now_year = 1970
for i in range(int(hash_years)):
    if year_remain > 365*86400: # 365-There might be a little bug.
        year_remain = year_remain - that_year(i)
    now_year = 1970 + i + 1


def that_month(m, this_year):
    """Calculate that mth month has how many seconds

       m: the m th month
       this_year: this year
    """
    if (m==1) or (m==3) or (m==5) or(m==7) or(m==8) or(m==10) or(m==12):
        that_month = 31 * 86400
    elif m == 2:
        if this_year % 4 == 0:
            that_month = 29 * 86400
        else:
            that_month = 28 * 86400
    else:
        that_month = 30 * 86400
    return that_month


month_remain = year_remain
now_month = 1
for i in range(12):
    if month_remain > 28*86400:
        month_remain = month_remain - that_month(i+1, now_year)
        now_month = (i + 1) + 1


day_remain = month_remain
now_day = day_remain//86400

hour_remain = day_remain % 86400
now_hour = hour_remain // 3600

min_remain = hour_remain % 3600
now_min = min_remain // 60

sec_remain = min_remain % 60
now_sec = int(sec_remain)

print("year", now_year, "month:", now_month, "day:", now_day, "hour:", now_hour, "min:", now_min, "sec:", now_sec)

```

第一版结果。

```Python
year 2017 month: 8 day: 1.0 hour: 9.0 min: 42.0 sec: 19
```

我们比英国早八小时，在它的基础上+8，就是我的当下时间：2017-08-02 17:42:19

第二版代码：

```python
import time
greenwichtime = time.time()

def that_year(n):
    """Calculate that nth year after 1970 has how many seconds

        n: the nth year after 1970
    """
    y = 1970 + n
    if (y % 4) == 0:
        that_year = 366 * 86400
    else:
        that_year = 365 * 86400
    return that_year


def that_month(m, this_year):
    """Calculate that mth month has how many seconds

       m: the m th month
       this_year: this year
    """
    if (m==1) or (m==3) or (m==5) or(m==7) or(m==8) or(m==10) or(m==12):
        that_month = 31 * 86400
    elif m == 2:
        if this_year % 4 == 0:
            that_month = 29 * 86400
        else:
            that_month = 28 * 86400
    else:
        that_month = 30 * 86400
    return that_month


def this_year(year_remain, k):
    now_year = 1970 + k
    year_remain = year_remain - that_year(k)
    print([year_remain, now_year])
    if year_remain < 0:
        year_remain = year_remain + that_year(k)
        return [year_remain, now_year]
    else:
        this_year(year_remain, k + 1)


now_year = this_year(greenwichtime, 0)[1]

print(now_year)

```

每年的数据都对，一直数到2017。但是函数返回值没有，只打印None。怎样用有结果的函数，怎样返回两个值，明天看下一章讲不讲。今天大致翻了一下，没有返回两个值的。在dash的python文档里搜function+return，没有谈这个问题。

```Python
...
[50059475.51102424, 2015]
[18437075.511024237, 2016]
[-13098924.488975763, 2017]
Traceback (most recent call last):
  File "/Users/johnqu/Projects/think_python3/code/greenwichtime_v2_john.py", line 46, in <module>
    now_year = this_year(greenwichtime, 0)[1]
TypeError: 'NoneType' object is not subscriptable
```

### 练习5.14-4，递归调用累计自然数相加

我写的docstring：

```Python
def recurse(n, s):
    """Calculate the integer n's addtion accumulation.

       eg. n = 5, recurse prints the result of 5 + 4 + 3 + 2 + 1
       thus:
       n: positive interger, if negative, it will exceed the maximum recursion depth around 992 extra.
       s: 0 is a prefered base. 
    """
    if n == 0:
        print(s)
    else:
        print("recurse", "n-->", n, "s-->", s)
        recurse(n-1, n+s)


recurse(5, 0)
```

如果用for语句写，可能是这个样子：

```Python
k = 0
for i in range(n)
    k = k + i + 1
print(k)
```

我是真的用3、用6演算过，从打印的状态表，才看出这函数在做加法。注意：print要在递归调用之前，打出来才是从定到底的状态表，否则是颠倒过来的。

```python
recurse n--> 5 s--> 0
recurse n--> 4 s--> 5
recurse n--> 3 s--> 9
recurse n--> 2 s--> 12
recurse n--> 1 s--> 14
15
```

## 有返回值的函数

2017-08-03，读完做完。今天就不贴代码，对比经验写在下图中了。（貌似越写越多）

![](https://ws3.sinaimg.cn/large/006tNc79gy1fi6psssvqdj30yu24odwq.jpg)

