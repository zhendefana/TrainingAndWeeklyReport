

## 补题

b题

[https://vjudge.csgrandeur.cn/problem/AtCoder-abc128_c]: 

思路：直接暴力模拟，用结构体存储，模拟亮不亮时用类似于桶排序的思想。

```c++
#include<iostream>
#include<string.h>
#include<algorithm>
using namespace std;
int a[1010];
int n,m,l,ans=0;
struct node
{
	int id,ll;
	int c[1010];
}q[1010];
int fun(int u)
{
	for(int i=1;i<=q[u].ll;i++){
		if(a[q[u].c[i]]==0) a[q[u].c[i]]=1;
		else a[q[u].c[i]]=0;
	}
}
int main()
{
	cin>>n>>m;
	cin>>l;
	for(int i=1;i<=l;i++){
		int x;
		cin>>x;
		a[x]=1;
	}
	for(int i=1;i<=n;i++){
		cin>>q[i].ll;
		for(int j=1;j<=q[i].ll;j++) cin>>q[i].c[j];
	}
	int i=1;
	for(i=1;i<=n;i++){
		fun(i);ans++;
		int k=1;
		for(k=1;k<=m;k++){
			if(a[k]!=0) break;
		}
		if(k>m){
			cout<<ans;
			return 0;
		}
	}
	i=1;
	for(i=1;i<=n;i++){
		fun(i);ans++;
		int k=1;
		for(k=1;k<=m;k++){
			if(a[k]!=0) break;
		}
		if(k>m){
			cout<<ans;
			return 0;
		}
	}
	if(i>n){
		cout<<-1;
		return 0;
	}
	return 0;
}

```
