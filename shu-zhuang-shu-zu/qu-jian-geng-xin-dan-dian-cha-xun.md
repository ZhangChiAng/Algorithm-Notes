# 区间更新单点查询

问题：[区间更新单点查询-树状数组](https://sunnywhy.com/camp/60/model/75?itemId=546)

```cpp
#include <iostream>
#include <string>
using namespace std;

const int MAX = 10001;
int a[MAX] = {0};   //a[i]表示区间(i - lowbit(i), i]的元素被加了多少

inline int lowbit(int i) {
    return i & -i;
}

void update(int k, int c) {
    for(int i = k; i > 0; i -= lowbit(i)) {
        a[i] += c;
    }
}

int get_sum(int k) {
    int sum = 0;
    for(int i = k; i < MAX; i += lowbit(i)) {
        sum += a[i];
    }
    return sum;
}

int main() {
    int n, m;
    cin >> n >> m;
    for(int i = 1; i <= n; i++) {
        int x;
        cin >> x;
        update(i, x);
        update(i - 1, -x);
    }
    while(m--) {
        string order;
        cin >> order;
        if(order == "Query") {
            int x;
            cin >> x;
            cout << get_sum(x) << '\n';
        } else if(order == "Add") {
            int l, r, c;
            cin >> l >> r >> c;
            update(r, c);
            update(l - 1, -c);
        } else {
            cout << "ERROR";
            return 0;
        }
    }
    return 0;
}

```
