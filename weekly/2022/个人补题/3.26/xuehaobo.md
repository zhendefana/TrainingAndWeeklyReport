## B题

[https://vjudge.csgrandeur.cn/contest/485267#problem/B]: 

思路：暴力枚举，枚举i和j，表示ab数组里，的每个数，记录相同，坐标相同和坐标不同的情况

```c++
#include<bits/stdc++.h>
using namespace std;
#define ll long long
#define MAXN 1048586
#define M 1005
#define N 500005
#define debug(...) cout << '[' << 'D' << 'E' << ']' << __LINE__ << ':' << __VA_ARGS__ << endl;
#define lv(x) #x << '(' << x << ')'
#define mod 998244353
#define who(s,limit,tpe) s + tpe , s + limit + tpe
#define all(s) s.begin(),s.end()
#define s_(s) s.size()
int a[N],b[N];
string s;
vector<int> G[N];
int main(){
    int n;
    ios::sync_with_stdio(false);
    cin.tie(0);
    cout.tie(0);
    cin >> n;
    for(int i = 1 ;i <= n ; i ++)
        cin >> a[i];
    for(int i = 1 ;i <= n ; i ++)
        cin >> b[i];
    int res = 0,sum = 0;
    for(int i = 1 ; i <= n ; i ++) {
        for(int j = 1 ; j <= n ; j ++) {
            if (i == j && a[i] == b[j]) sum ++; // 坐标相同
            else if (i != j && a[i] == b[j]) res ++; // 坐标不同
        }
    }
    cout << sum << endl << res << endl;
}
```

