
### ある値が二乗かを判定する関数

```cpp
bool is_sqrt(int n) {
   if(floor(sqrt(n))==sqrt(n)) {
       return true;
   } else {
       return false;
   }
}

bool is_sqrt(long long n) {
   if(floor(sqrt(n))==sqrt(n)) {
       return true;
   } else {
       return false;
   }
}

```

### mapの使い方
findはvectorでも使用できるので覚えておく。

```cpp
// map<key, value>の形で表現
map<string, int> m = {};

// map.emplace("key", value);
// 値を挿入する
m.emplace("hello", 1);
m.emplace("world", 2);
cout << m["hello"] << " " << m["world"] << endl;

// map.find("key")
// keyの値を探す。存在しなければ最後尾のイテレーターを返す
// output NOT FOUND!!

auto iter = m.find("aaa");
if (iter != m.end()) {
    cout << "key: " << iter->first << ", value: " << iter->second << "\n";
} else {
    cout << "NOT FOUND!!" << endl;
}

// m.find
// output 1
auto iter2 = m.find("hello");
if (iter2 != m.end()) {
    cout << "key: " << iter2->first << ", value: " << iter2->second << "\n";
    iter2->second++;
} else {
    cout << "NOT FOUND!!" << endl;
}

// output 2
cout << m["hello"] << endl;
```

#### map全探索

```cpp
map<string, int> mp;

for(auto itr = mp.begin(); itr != mp.end(); ++itr) {
    // 何らかの処理
}
```

### fillでの初期化のやり方

```cpp
int a[] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
//初期化
//output 1 1 1 1 5 6 7 8 9 10 
fill(a, a+4, 1);
for(int i = 0;i < 10;i++) {
    cout << a[i] << " ";
}
cout << "\n";

bool flags[1000];
fill(flags, flags+1000, true);
```

### double型の出力範囲を広げるには？

```cpp
cout << fixed << setprecision(15)<<(l/3)*(l/3)*(l/3) << endl;
```


### 最小公倍数、最大公約数を出力
(参考サイト https://qiita.com/e869120/items/518297c6816adb67f9a5)

```cpp
// 例 1: 2 つの整数 a, b を入力し、a と b の最大公約数と最小公倍数を出力する
int a, b;
cin >> a >> b;
cout << __gcd(a, b) << endl;
cout << a / __gcd(a, b) * b << endl;
```

### 実行時間計測
(参考サイト https://qiita.com/e869120/items/518297c6816adb67f9a5)

```cpp
int ti = clock();
for (int i = 1; i <= 1000000; i++) cout << i << endl;
printf("Execution Time: %.4lf sec\n", 1.0 * (clock() - ti) / CLOCKS_PER_SEC);
return 0;
```

### reverse逆順に並び替える
(参考サイト https://qiita.com/e869120/items/518297c6816adb67f9a5)

```cpp
// 例 1: 配列 a の 2～6 番目の要素を逆順にします。{8, 3, 2, 6, 4, 1, 7, 5} に変化します。
int a[8] = {8, 3, 7, 1, 4, 6, 2, 5};
reverse(a + 2, a + 7);
for (int i = 0; i < 8; i++) cout << a[i] << " ";
cout << "\n";
// 例 2: {b[0], b[1], ..., b[N-1]} を入力し、逆順にしたうえで出力します。
int N, b[1009];
cin >> N;
for (int i = 0; i < N; i++) cin >> b[i];
reverse(b, b + N);
for (int i = 0; i < N; i++) cout << b[i] << " ";
cout << "\n";
return 0;
```

### int to string

```cpp
int a;
cin >> a;
cout << to_string(a) << endl;
```

### setの使い方

```cpp
int n;
cin >> n;
set<char> mp;
for(int i = 0;i < n;i++) {
    char x;
    cin >> x;
    // 挿入
    mp.insert(x);
}
mp.size() // 大きさ
```