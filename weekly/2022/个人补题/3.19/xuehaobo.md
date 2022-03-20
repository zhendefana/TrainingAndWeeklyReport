## 补题

c题

[https://vjudge.csgrandeur.cn/problem/AtCoder-abc242_c]: 

题解：运用数位dp求解

```c++
#include<bits/stdc++.h>
using namespace std;
const int maxn=1e6+5,mod = 998244353;
long  long dp[maxn][10];
int main()
{
	for(int i=1;i<=9;i++)
	dp[1][i]=1;
	long long n;
	cin>>n;
	for(int i=1;i<=n;i++)
	{
		for(int j=1;j<=9;j++)
		{
		dp[i][j]=(dp[i][j]+dp[i-1][j])%mod;
		if(j-1>=1)
		dp[i][j]=(dp[i][j]+dp[i-1][j-1])%mod;
		if(j+1<=9)
		dp[i][j]=(dp[i][j]+dp[i-1][j+1])%mod;	
		}	
	}
	long long sum=0;
	for(int i=1;i<=9;i++)
	{
		sum+=dp[n][i];
		sum=sum%mod;
	}
	cout<<sum<<endl;
}

```

