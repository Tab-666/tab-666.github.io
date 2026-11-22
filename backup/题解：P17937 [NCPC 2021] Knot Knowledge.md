# [P17937 [NCPC 2021] Knot Knowledge](https://www.luogu.com.cn/problem/P17937) 题解
## 讲解
签到题，建议评红。

### 思路
思路其实就是一个公式：完整列表的总和 − 已学列表的总和 = 漏掉的那个数。

为什么这样求？

因为已学列表就是完整列表少了一个数，其他数都一模一样。

把两边分别加起来，相同的数会互相抵消，最后只剩下那个没学的数。

### 代码流程
定义 n，输入 n。

定义两个变量 s1 和 s2，分别存储要学习的绳结编号和学会的绳结编号。

循环 n 次，把每次输入的数字 x 累加到 s1 中。

循环 n-1 次，把每次输入的数字 y 累加到 s2 中。

最后输出 s1-s2 的值即可！

## 代码
```cpp
#include <bits/stdc++.h>
using namespace std;
int main(){
    int n;
    cin>>n;
    int s1=0,s2=0;
    for(int i=1;i<=n;i++){
        int x;
        cin>>x;
        s1+=x;
    }
    for(int i=1;i<=n-1;i++){
        int y;
        cin>>y;
        s2+=y;
    }
    cout<<s1-s2;
    return 0;
}
```