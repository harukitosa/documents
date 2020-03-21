
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