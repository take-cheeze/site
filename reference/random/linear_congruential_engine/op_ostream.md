#operator<<(C++11)
```cpp
namespace std {
  template <class CharT, class Traits,
            class UIntType, UIntType A, UIntType C, UIntType M>
  basic_ostream<CharT, Traits>& operator<<(
    basic_ostream<CharT, Traits>& os
    const linear_congruential_engine<UIntType, A, C, M>& x);
}
```
* basic_ostream[link /reference/iostream/basic_ostream.md]

##概要
ストリームへの出力を行う。


##効果
`os`に対してフォーマットフラグ`ios_base::dec | ios_base::left`を設定する。  
フォーマットを設定した`os`に対して、エンジン`x`の現在状態を出力する。


##事後条件
`os`のフォーマットフラグが、この関数を呼び出す前の状態に戻ること。


##戻り値
`os`


##例
```cpp
#include <iostream>
#include <random>

int main()
{
  std::minstd_rand engine;
  std::cout << engine << std::endl;
}
```

###出力例
```
1
```

##バージョン
###言語
- C++11

###処理系
- [Clang](/implementation#clang.md): ??
- [GCC](/implementation#gcc.md): 
- [GCC, C++0x mode](/implementation#gcc.md): 4.7.2
- [ICC](/implementation#icc.md): ??
- [Visual C++](/implementation#visual_cpp.md) ??


##参照


