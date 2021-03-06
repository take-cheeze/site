#rank(C++11)
```cpp
namespace std {
  template <class T>
  struct rank {
    typedef … type;
  };
}
```

##概要
配列型の次元数を取得する。


##効果
型`T`が配列型である場合、配列の次元数となる整数値をメンバ定数`value`の値として定義する。配列型でなければ`0`をメンバ定数`value`の値として定義する。


##例
```cpp
#include <type_traits>

static_assert(std::rank<int>::value == 0, "int rank is 0");
static_assert(std::rank<int[3]>::value == 1, "int[3] rank is 1");
static_assert(std::rank<int[3][4]>::value == 2, "int[3][4] rank is 2");

int main() {}
```

###出力
```
```

##バージョン
###言語
- C++11

###処理系
- [Clang](/implementation#clang.md): 3.0
- [GCC, C++0x mode](/implementation#gcc.md): 4.3.6
- [Visual C++](/implementation#visual_cpp.md): ??


