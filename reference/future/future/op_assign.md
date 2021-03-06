#代入演算子(C++11)
```cpp
future& operator=(const future& rhs) = delete;
future& operator=(future&& rhs) noexcept;
```

##概要
- `future& operator=(const future& rhs) = delete;`<br/>コピー代入。コピー不可。
- `future& operator=(future&& rhs) noexcept;`<br/>ムーブ代入。効果： 共有状態を解放し、`rhs`の共有状態を含むコンテンツを`*this`にムーブ代入する。事後条件： [`valid()`](./valid.md)の戻り値が、この関数を呼び出す前の`rhs.`[`valid()`](./valid.md)と等価になること。`rhs.`[`valid()`](./valid.md)` == false`になること。<br/>戻り値： `*this`<br/>例外： 投げない

##例
```cpp
#include <future>

int main()
{
  std::promise<int> p;
  std::future<int> f;
  f = p.get_future();
}
```

###出力
```
```

##バージョン
###言語
- C++11

###処理系
- [Clang](/implementation#clang.md): ??
- [GCC](/implementation#gcc.md): 
- [GCC, C++0x mode](/implementation#gcc.md): 4.7.0
- [ICC](/implementation#icc.md): ??
- [Visual C++](/implementation#visual_cpp.md): 11.0


##参照


