# 素数

#### 素数的判断

```cpp
bool is_prime(int n) {
    if(n <= 1)
        return false;
    int sqr = (int)sqrt(1.0 * n);
    for(int i = 2; i <= sqr; i++) {
        if(n % i == 0)
            return false;
    }
    return true;
}
```

#### 素数表的获取

```cpp
//筛法，时间复杂度O(nloglogn)
void find_prime(bool composite[], vector<int>& primes) {
    for(int i = 2; i <= MAX; i++) {
        if(composite[i])
            continue;
        primes.push_back(i);
        for(int j = i + i; j <= MAX; j += i) {
            composite[j] = true;
        }
    }
}
```
