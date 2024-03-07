# 最大公约数、最小公倍数、互质

#### 最大公约数

欧几里得算法：设a、b均为正整数，则gcd(a, b) = gcd(b, a % b)。

```cpp
int gcd(int a, int b) {
    return !b ? a : gcd(b, a % b);
}
```

#### 最小公倍数

```cpp
int lcm(int a, int b) {
    return a / gcd(a, b) * b;
}
```

#### 互质

如果两个正整数a、b的最大公约数是1，那么称a、b是互质的。
