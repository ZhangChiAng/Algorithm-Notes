# 二维

问题：[实时子矩阵和-二维树状数组](https://sunnywhy.com/camp/60/model/75?itemId=545)

```cpp
#include <iostream>
#include <string>
using namespace std;

const int MAX = 101;
int a[MAX][MAX] = {0};
int n, m, k;

inline int lowbit(int i) {
    return i & -i;
}

void update(int x, int y, int v) {
    for(int i = x; i <= n; i += lowbit(i)) {
        for(int j = y; j <= m; j += lowbit(j)) {
            a[i][j] += v;
        }
    }
}

int get_sum(int x, int y) {
    int sum = 0;
    for(int i = x; i > 0; i -= lowbit(i)) {
        for(int j = y; j > 0; j-= lowbit(j)) {
            sum += a[i][j];
        }
    }
    return sum;
}

int main() {
    cin >> n >> m >> k;
    while(k--) {
        string op;
        cin >> op;
        if(op == "Add") {
            int i, j, v;
            cin >> i >> j >> v;
            update(i, j, v);
        } else if(op == "Query") {
            int r1, c1, r2, c2;
            cin >> r1 >> c1 >> r2 >> c2;
            cout << (get_sum(r2, c2) -get_sum(r1 - 1, c2) -get_sum(r2, c1 - 1) + get_sum(r1 - 1, c1 - 1)) << '\n';
        } else {
            cout << "ERROR";
            return 0;
        }
    }
    return 0;
}

```
