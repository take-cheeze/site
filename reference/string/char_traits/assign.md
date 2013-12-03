#assign
```cpp
// C++03まで
static void assign(char_type& c1, const char_type& c2);        // (1)
static char_type* assign(char_type* s, size_t n, char_type a); // (2)

// C++11以降
static void assign(char_type& c1, const char_type& c2) noexcept; // (1)
static char_type* assign(char_type* s, size_t n, char_type a);   // (2)
```

##概要
左辺に右辺を代入する。


##効果
- (1) 標準で定義される`char_traits`の特殊化では、`c1 = c2`により代入を行う。
- (2) 長さ`n`の文字列`s`の各要素に`a`を代入する。


##戻り値
- (1) なし
- (2) 代入完了後の`s`を返す。


##計算量
- (1) 定数時間
- (2) 線形時間

##例
```cpp
#include <iostream>
#include <string>

int main()
{
  char c = 'a';
  std::char_traits<char>::assign(c, 'b');

  std::cout << c << std::endl;
}
```

###出力
```
b
```

##参照
