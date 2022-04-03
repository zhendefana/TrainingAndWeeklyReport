## 补题

c题

[[Yamanote Line Game - AtCoder abc244_c - Virtual Judge (csgrandeur.cn)](https://vjudge.csgrandeur.cn/problem/AtCoder-abc244_c)]: 

题意：给定一个数n，双方需要在1 ~( 2 * n + 1 )中选择一个数打印，之前打印过的数不能够再打印，直至其中一方找不到打印数为止。

题解：用一个set存下所以可以打印的数，每次打印完就把这个数从set中删除，我们输出时，每次输出这个set的最小数即可。

```c++
#include<bits/stdc++.h>
 
typedef long long ll;
typedef unsigned long long ull;
 
const int N = 2e5+10,M = N * 2,INF = 0x3f3f3f3f,P = 9901;
 
int query()
{
    int x;
    std::cin>>x;
    return x;
}
 
void solve()
{
    int n;
    std::cin>>n;
    std::set<int> st;
    for(int i = 1 ; i <= 2 * n + 1; i++)st.insert(i);
    while(true)
    {
        std::cout<<*st.begin()<<std::endl;
        st.erase(st.begin());
        int x = query();
        if(x==0)break;
        st.erase(x);
    }
}
 
int main()
{
    std::ios::sync_with_stdio(false);
    std::cin.tie(nullptr);
    std::cout.tie(nullptr);
    {
        solve();
    }
    return 0;
}
```

