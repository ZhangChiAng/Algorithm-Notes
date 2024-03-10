# 与二分查找结合

问题：[数据流第K大元素-树状数组](https://sunnywhy.com/camp/60/model/75?itemId=543)

```cpp
#include <iostream>
#include <string>
using namespace std;

const int MAXN = 10001;
int a[MAXN] = {0};  //a[i] = num of (i - lowbit(i), i]

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

int find_k(int k) {
    int l = 1, r = MAXN;
    while(l < r) {
        int mid = (l + r) / 2;
        if(get_sum(mid) >= k) {
            r = mid;
        } else {
            l = mid + 1;
        }
    }
    return (l != MAXN ? l : -1);
}

int main() {
    int n;
    cin >> n;
    while(n--) {
        string order;
        int tmp;
        cin >> order >> tmp;
        if(order == "Push") {
            update(tmp, 1);
        } else if(order == "Print") {
            cout << find_k(tmp) << '\n';
        } else {
            cout << "ERROR";
        }
    }
    return 0;
}

```
