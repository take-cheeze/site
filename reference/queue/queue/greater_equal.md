#operator>=
```cpp
namespace std {

  template <class T, class Container>
  bool operator>=(const queue<T, Container>& x, const queue<T, Container>& y);

}
```

##概要

<b>queueにおいて、左辺が右辺以上かを判定する。</b>



##戻り値

`x.c >= y.c`

##備考



##例

```cpp
#include <iostream>
#include <queue>

int main ()
{
  std::queue<int> x;
  x.push(4);
  x.push(5);
  x.push(6);

  std::queue<int> y;
  y.push(1);
  y.push(2);
  y.push(3);

  std::cout << std::boolalpha << (x >= y) << std::endl;
}
```
* >=[color ff0000]

###出力

```cpp
true
```

##参照

