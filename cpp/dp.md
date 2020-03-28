## ナップザック問題

```cpp
/**
 * ナップサック問題を解く関数
 * 
 * @param m ナップザックの大きさ
 * @param size　品物の大きさを表す配列
 * @param value 品物の価値を表す配列
 * 
 * return 合計の価値 err -1
 */
int knapsack(int m, vector<int> size, vector<int> value)
{
    if (size.size() != value.size())
    {
        return -1;
    }
    int N = size.size();
    int total[m + 1];
    fill(total, total + m + 1, 0);
    int choice[m + 1];
    fill(choice, choice + m + 1, -1);
    int repackTotal;

    for (int i = 0; i < N; i++)
    {
        for (int j = size[i]; j <= m; j++)
        {
            repackTotal = total[j - size[i]] + value[i];
            if (repackTotal > total[j])
            {
                total[j] = repackTotal;
                choice[j] = i;
            }
        }
    }
    return total[m];
}

int main()
{
    cin.tie(0);
    ios::sync_with_stdio(false);
    int n;
    int m;
    cin >> n >> m;
    vector<int> size;
    vector<int> value;
    for (int i = 0; i < n; i++)
    {
        int x, y;
        cin >> x >> y;
        size.push_back(x);
        value.push_back(y);
    }
    cout << knapsack(m, size, value) << endl;
}
```

### 入力
```
5 10
2 2
3 4
5 7
7 11
9 14
```

### 動作確認

```
ナップザックの大きさは10
i = 0
total = 0 0 2 2 4 4 6 6 8 8 10 
choice = -1 -1 0 0 0 0 0 0 0 0 0 
i = 1
total = 0 0 2 4 4 6 8 8 10 12 12 
choice = -1 -1 0 1 0 1 1 1 1 1 1 
i = 2
total = 0 0 2 4 4 7 8 9 11 12 14 
choice = -1 -1 0 1 0 2 1 2 2 1 2 
i = 3
total = 0 0 2 4 4 7 8 11 11 13 15 
choice = -1 -1 0 1 0 2 1 3 2 3 3 
i = 4
total = 0 0 2 4 4 7 8 11 11 14 15 
choice = -1 -1 0 1 0 2 1 3 2 4 3 
品物3価値11を詰め込む
品物1価値4を詰め込む
15
```