#operator>>
```cpp
template <class CharT, class Traits, class Allocator>
basic_string operator>>(basic_istream<CharT, Traits>& is, basic_string<CharT, Traits, Allocator>& str);
```

##概要
文字列を入力する。空白文字が現れるまで、あるいは`setw`マニピュレータで指定された数までの文字を入力する。

この関数は、書式化入力関数（[`basic_istream`](../../istream/basic_istream.md)を参照）として作用する。

## 効果
1. [`basic_istream<>::sentry`](../../istream/basic_istream/sentry.md)オブジェクトを構築する。`sentry`オブジェクトが失敗を示した場合、何もしない。
1. `str.erase()`を呼び出す。
1. 以下のいずれかを満たすまで、文字を入力して`str.append(1, c)`と等価な方法で文字列に追加する。なお、`c`は入力した文字を表す。
    - 最大文字数まで書き込んだ場合。最大文字数は次のいずれかである。
        - `is.width()`が`0`以上ならその値とする。
        - さもなくば、`str.max_size()`とする。
    - EOFに達した場合。
    - 空白文字に達した場合。空白文字の判定にはストリームに設定されているロケールが考慮される。
1. `is.width(0)`を呼び出す。

`str`に1文字も入力が行われなかった場合、`is.setstate(ios_base::failbit)`が呼び出される。

##戻り値
- 仮引数`is`。


##例
```cpp
#include <iostream>
#include <string>

int main()
{
  std::string a, b;
  std::cin >> a >> b;
  std::cout << a << std::endl;
  std::cout << b << std::endl;
}
```

###入力
```
Apple Banana
```

###出力
```
Apple
Banana
```

##参照