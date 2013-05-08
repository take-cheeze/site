#operator!=
```cpp
namespace std {
  template <class T, class Allocator>
  bool operator!=(const vector<T, Allocator>& x,const vector<T, Allocator>& y);
}
```

##概要

<b>vectorの非等値比較を行う。</b>


##要件

型`T`が`operator==`で比較可能であること。


##戻り値

`!(x [==](/reference/vector/op_equal.md) y)`


##計算量

線形時間


##例

```cpp
#include <iostream>
#include <vector>

int main ()
{
  std::vector<int> v1 = {1, 2, 3};
  std::vector<int> v2 = {1, 2, 3};
  std::vector<int> v3 = {1, 2, 3, 4};

  std::cout << std::boolalpha;

  // 要素数と要素の値が等しい
  std::cout << (v1 != v2) << std::endl;

  // 要素の値は(左辺の要素数分まで)等しいが要素数が異なる
  std::cout << (v1 != v3) << std::endl;
}
```
* !=[color ff0000]
* !=[color ff0000]

###出力

```cpp
false
true
```

##参照

