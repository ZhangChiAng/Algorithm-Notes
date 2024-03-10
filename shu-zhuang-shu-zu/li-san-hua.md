# 离散化

问题：[统计左侧较小数-离散化](https://sunnywhy.com/camp/60/model/75?itemId=542)

```cpp
#include <iostream>
#include <vector>
#include <map>
using namespace std;

const int MAX = 10001;
int a[MAXN] = {0};  //a[i]表示位于区间(i - lowbit(i), i]的元素个数

inline int lowbit(int i) {
    return i & -i;
}

void update(int x, int k) {
    for(int i = x; i < MAXN; i += lowbit(i)) {
        a[i] += k;
    }
}

int get_sum(int x) {
    int sum = 0;
    for(int i = x; i > 0; i -= lowbit(i)) {
        sum += a[i];
    }
    return sum;
}

int main() {
    int n;
    cin >> n;
    vector<int> v(n);
    map<int, int> mp;
    for(int i = 0; i < n; i++) {
        cin >> v[i];
        mp[v[i]] = 0;
    }
    //离散化
    int index = 1;
    for(auto it = mp.begin(); it != mp.end(); it++) {
        it->second = index++;
    }
    for(int i = 0; i < n; i++) {
        update(mp[v[i]], 1);
        if(i) {
            cout<<' ';
        }
        cout << get_sum(mp[v[i]] - 1);
    }
    return 0;
}

```
