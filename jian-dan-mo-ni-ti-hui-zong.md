---
description: '题目怎么说,你就怎么做,一般不涉及算法,完全是根据题目描述来进行代码的编写,所以考察的是代码能力'
---

# 简单模拟题汇总

1001 A+B Format \(20分\)

Calculate a+b and output the sum in standard format -- that is, the digits must be separated into groups of three by commas \(unless there are less than four digits\).

#### Input Specification: <a id="input-specification-"></a>

Each input file contains one test case. Each case contains a pair of integers a and b where −10​6​​≤a,b≤10​6​​. The numbers are separated by a space.

#### Output Specification: <a id="output-specification-"></a>

For each test case, you should output the sum of a and b in one line. The sum must be written in the standard format.

#### Sample Input: <a id="sample-input-"></a>

```cpp
-1000000 9
```

#### Sample Output: <a id="sample-output-"></a>

```cpp
-999,991
```

解题关键思路:主要是解决添加逗号的位置,我们应该从开头进行添加,解决办法是加上`(i+1)%3==len%3`  而且最后一个位置不用加上

代码

```cpp
#include<iostream>//不想OI一场空，千万别用万能头
#include<algorithm>//快排sort()
#include<cstdio>//能不用cin就不用
#include<cstring>
#include<cmath>
#include<map>
#include<vector>
#include<queue>
#include<set>
#define IL inline
using namespace std;
int main(){
    int a,b,flag=1;
    cin>>a>>b;
    string str;
    str=to_string(a+b);
    int len=str.size();
    for(int i=0;i<len;i++)
    {
     cout<<str[i];
     if (str[i]=='-')continue;
     if ((i+1)%3==len%3&&i!=len-1)cout<<",";
    }

    return 0;

}


```

