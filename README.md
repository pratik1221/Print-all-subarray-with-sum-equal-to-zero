// INDIAN ARMY
//mahi7781
#include<bits/stdc++.h>
#define teji ios_base::sync_with_stdio(false);cin.tie(NULL)
using namespace std;
#define ll long long int
#define mod 1000000007
#define pb push_back
#define ss second
#define ff first
#define mp make_pair
#define lb lower_bound
#define ub upper_bound
#define pii pair<int,int>
#define f(i,x,n) for(ll i=x;i<n;i++)
int main()
{
    ll t=1;
    // cin>>t;
    while(t--)
    {
      ll n;
      cin>>n;
      ll a[n];
      ll odd,even;
      odd=even=0;
      f(i,0,n)
      cin>>a[i];
     
      vector<pii>v;
      map<ll,vector<ll>>map;
      ll sum=0;
      f(i,0,n)
      {
        sum=sum+a[i];
        if(sum==0)
        v.pb({0,i});

        if(map.find(sum)!=map.end())
        {
          vector<ll>v2=map[sum];
          for(auto it=v2.begin();it!=v2.end();it++)
          v.pb({*it+1,i});
        }
        map[sum].pb(i);
      
      }
      // cout<<v.size();
      for(auto it=v.begin();it!=v.end();it++)
      {
        f(i,it->ff,it->ss+1)
        cout<<a[i]<<" ";
        cout<<endl;
      }     
      

    }
}
