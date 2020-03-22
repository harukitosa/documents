
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

mapの使い方

```cpp
// map<key, value>の形で表現
map<string, int> m = {};
// 値を挿入する
m.emplace("hello", 1);
m.emplace("world", 2);
cout << m["hello"] << " " << m["world"] << endl;

// map.find("key")
// keyの値を探す。存在しなければ最後尾のイテレーターを返す
auto iter = m.find("Alice");
if (iter != m.end()) {
    cout << "key: " << iter->first << ", value: " << iter->second << "\n";
} else {
    // out put NOT FOUND!!
    cout << "NOT FOUND!!" << endl;
}

// m.find
auto iter2 = m.find("hello");
if (iter2 != m.end()) {
    // output 1
    cout << "key: " << iter2->first << ", value: " << iter2->second << "\n";
    iter2->second++;
} else {
    cout << "NOT FOUND!!" << endl;
}

// output 2
cout << m["hello"] << endl;
```