### combinationの2を求める関数
二つを選びなさいで使用する。

```cpp
long long combi2(long long n) {
    return n*(n-1)/2;
}
```

### 回文かどうかを判定する関数
回文 -> true
回文じゃない -> false

```cpp
bool is_kaibun(string s) {
   bool flag = true;
   int n = s.length();
   for(int i = 0;i < n;i++) {
      if(s[i] != s[n-i-1]) {
         flag = false;
      }
   }
   return flag;
}
```