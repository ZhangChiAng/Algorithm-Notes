# 单点更新区间查询

问题：[单点更新区间查询-树状数组](https://sunnywhy.com/camp/60/model/75?itemId=539)

```cpp
#include <iostream>
#include <vector>
#include <string>
using namespace std;

vector<int> v;

inline int lowbit(int i) {
    return i & -i;
}

void update(int k, int c) {
    for(int i = k; i < v.size(); i += lowbit(i)) {
        v[i] += c;
    }
}

int get_sum(int k) {
    int sum = 0;
    for(int i = k; i > 0; i -= lowbit(i)) {
        sum += v[i];
    }
    return sum;
}

int main() {
    int n, m;
    cin>>n>>m;
    v = vector<int>(n + 1, 0);
    for(int i = 1; i <= n; i++) {
        int x;
        cin>>x;
        update(i, x);
    }
    while(m--) {
        string order;
        cin>>order;
        if(order == "Add") {
            int k, c;
            cin>>k>>c;
            update(k, c);
        } else if(order == "Query") {
            int l, r;
            cin>>l>>r;
            cout<<get_sum(r) - get_sum(l - 1)<<'\n';
        } else {
            cout<<"ERROR";
            return 0;
        }
    }
    return 0;
}

```
