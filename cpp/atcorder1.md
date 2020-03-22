
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