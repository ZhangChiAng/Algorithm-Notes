# 组合数

[组合数的计算](https://sunnywhy.com/sfbj/5/8/232)

利用递推公式计算：

```cpp
//递归
#include <cstdio>

typedef long long ll;
ll res[67][67] = {0};

ll C(ll n, ll m) {
    if(m == 0 || m == n) {
        return 1;
    }
    if(res[n][m] != 0) {
        return res[n][m];
    }
    res[n][m] = C(n - 1, m) + C(n - 1, m - 1);
    return res[n][m];
}

int main() {
    ll n, m;
    scanf("%lld%lld", &n, &m);
    printf("%lld", C(n, m));
}
```

```cpp
//递推
ll res[MAX][MAX] = {0};

ll C(int n, int m) {
    for(int i = 0; i <= n; i++) {
        res[i][0] = res[i][i] = 1;
    }
    for(int i = 2; i <= n; i++) {
        for(int j = 1; j <= i / 2; j++) {
            res[i][j] = res[i][i - j] =
                res[i - 1][j] + res[i - 1][j - 1];
        }
    }
    return res[n][m];
}
```

通过定义式的变形来计算：

```cpp
ll C(ll n, ll m) {
    ll res = 1;
    for(int i = 1; i <= m; i++) {
        res = res * (n - m + i) / i;
    }
    return res;
}
```
