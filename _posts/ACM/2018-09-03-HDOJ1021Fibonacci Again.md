---
layout : life
title : "HDOJ1021 Fibonacci Again"
category : ACM
duoshuo : true
date : 2018-09-03
---

作者:没有语言的傻子

日期:2018年09月03日

摘要:HDOJ1021 Fibonacci Again


<!-- more -->

<h1><center><a href="http://acm.hdu.edu.cn/showproblem.php?pid=1021">Fibonacci Again</a></center></h1>

<center>
Time Limit: 2000/1000 MS (Java/Others)    Memory Limit: 65536/32768 K (Java/Others)
Total Submission(s): 72792    Accepted Submission(s): 33298
</center>

## Problem Description

There are another kind of Fibonacci numbers: F(0) = 7, F(1) = 11, F(n) = F(n-1) + F(n-2) (n>=2).

## Input

Input consists of a sequence of lines, each containing an integer n. (n < 1,000,000).

## Output

Print the word "yes" if 3 divide evenly into F(n).
Print the word "no" if not.

## Sample Input

```bash
0
1
2
3
4
5
```

## Sample Output

```bash
no
no
yes
no
no
no
```

## Author

Leojay

## Code

这是一道规律题,将Fibonacci数列对3取模输出后,可以发现是一个周期为8的数列.

```C++
#include <cstdio>
int main()
{
    freopen("in.txt", "r", stdin);
    int n;
    while(~scanf("%d", &n))
        if(n % 8 == 2 || n % 8 == 6) printf("yes\n");
        else printf("no\n");
    return 0;
}
/*
错误的代码
#include <iostream>
using namespace std;
const int maxn = 1000000 + 5;
long long fi[maxn];
int main()
{
    freopen("in.txt", "r", stdin);
    int fin = 2;
    int n;
    fi[0] = 7;
    fi[1] = 11;
    while(~scanf("%d", &n))
    {
        if(fin <= n)
        {
            for(int i = fin; i <= n; i++)
                fi[i] = fi[i - 1] + fi[i - 2];
            fin = n;
        }
        if(fi[n] % 3 == 0)
            printf("yes\n");
        else
            printf("no\n");
    }
    return 0;
}
*/
```