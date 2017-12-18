#include <bits/stdc++.h>
using namespace std;
#define MAXI 1000000007;
long long int n1,n2,n3,n4;
void fibonacci(long long int n,long long int fib[])
{
    if(n == 0)
    {
        fib[0] = 0;
        fib[1] = 1;
        return;
    }
    fibonacci((n/2),fib);
    n1 = fib[0];             
    n2 = fib[1];             
    n3 = 2*n2 - n1;
    if(n3 < 0)
        n3 += MAXI;
    n3 = (n1 * n3) % MAXI;      
    n4 = (n1*n1 + n2*n2) % MAXI;  
    if(n%2 == 0)
    {
        fib[0] = n3;
        fib[1] = n4;
    }
    else
    {
        fib[0] = n4;
        fib[1] = n3+n4;
    }
}
int main()
{
    long long int t;
    cin>>t;
    while(t--){
          long long int n;        
          cin>>n;
          long long int fib[2]={0};
          fibonacci(n+2,fib);
          printf("%lld\n",fib[0]);
    }
    return 0;
}
