#max_size
```cpp
size_type max_size() const noexcept;
```

##概要
`set` コンテナが格納できる要素の最大数を返す。 
これは、システムやライブラリ実装の制限のもとでコンテナが格納できる潜在的な最大サイズである。


##戻り値
`set` コンテナが自身のコンテンツとして保持できる要素の最大数。 
メンバ型 `size_type` は符号なし整数型である。


##計算量
定数時間。


##例
```cpp
#include <iostream>
#include <set>
using namespace std;
 
int main ()
{
  set<int> c;
  
  cout << c.max_size();
  
  return 0;
}
```

###出力例
```
1073741823
```

##参照

| | |
|-----------------------------------------------------------------------------------|--------------------------|
| [`size`](./size.md) | 要素数を取得する |

