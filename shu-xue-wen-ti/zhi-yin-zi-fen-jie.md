# 质因子分解

问题：[质因子分解](https://sunnywhy.com/sfbj/5/5/212)

```cpp
#include <cstdio>
#include <cmath>
#include <vector>
using namespace std;

//对一个正整数来说，如果它存在[2, n]范围内的质因子，
//要么这些质因子全部小于等于sqrt(n)，
//要么只存在一个大于sqrt(n)的质因子，而其余质因子全部小于等于sqrt(n)
const int MAX = 1e3 + 1;
bool composite[MAX] = {false};
vector<int> primes;
struct factor {
    int f, cnt;
}factors[10];    //factors数组的大小只需要开到10就可以了

void find_prime() {
    for(int i = 2; i < MAX; i++) {
        if(composite[i]) {
            continue;
        }
        primes.push_back(i);
        for(int j = i + i; j < MAX; j += i) {
            composite[j] = true;
        }
    }
}

int main() {
    find_prime();
    int n;
    scanf("%d", &n);
    
    int sqr = (int)sqrt(1.0 * n);
    int m = 0;
    for(int i = 0; i < primes.size() && primes[i] <= sqr; i++) {
        if(n % primes[i] == 0) {
            factors[m].f = primes[i];
            factors[m].cnt = 0;
            while(n % primes[i] == 0) {
                factors[m].cnt++;
                n /= primes[i];
            }
            m++;
        }
        if(n == 1) {
            break;
        }
    }
    //处理大于sqrt(n)的因子
    if(n != 1) {
        factors[m].f = n;
        factors[m].cnt = 1;
        m++;
    }

    for(int i = 0; i < m; i++) {
        printf("%d %d\n", factors[i].f, factors[i].cnt);
    }
}

```
