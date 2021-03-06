#operator=
```cpp
multimap<Key,T,Compare,Allocator>& operator=(const multimap<Key,T,Compare,Allocator>& x);

// since C++11
multimap<Key,T,Compare,Allocator>& operator=(multimap<Key,T,Compare,Allocator>&& y);

// since C++11
multimap& operator=(initializer_list<value_type> init);
```

##概要
- `multimap<Key,T,Compare,Allocator>& operator=(const multimap<Key,T,Compare,Allocator>& x)`<br/>`x`に格納されている要素のコピーをコンテナの新しい要素とする。<br/>この呼び出しの前に格納されていた要素は取り除かれ、`x` に格納されている要素のそれぞれのコピーによって置き換えられる。<br/>このメンバ関数の呼び出しの後、`multimap` オブジェクトと `x` は同じサイズになり、比較すると互いに等しくなる。
- `multimap<Key,T,Compare,Allocator>& operator=(multimap<Key,T,Compare,Allocator>&& y)`<br/>`y` に格納されている要素をムーブしてコンテナの新しい要素とする。<br/>この呼び出しの前に格納されていた要素は取り除かれ、`y` に格納されていた要素がムーブされることで置き換えられる。
- `multimap& operator=(initializer_list<value_type> init)`<br/>`init` で指定した要素をコンテナの新しい要素とする。<br/>この呼び出しの前に格納されていた要素は取り除かれ、`init` で指定した要素によって置き換える


##パラメータ
- `x`<br/>
コンテンツのコピー元となる、テンプレートパラメータ(`Key, T, Compare, Allocator`)が同じ `multimap` オブジェクト。 

- `y`<br/>
コンテンツのムーブ元となる、テンプレートパラメータ(`Key, T, Compare, Allocator`)が同じ `multimap` オブジェクト。 

- `init`<br/>
メンバ型 `value_type` と同じ型の `initializer_list`。


##戻り値
`*this`


##計算量
- `multimap<Key,T,Compare,Allocator>& operator=(const multimap<Key,T,Compare,Allocator>& x)`
- `multimap& operator=(initializer_list<value_type> init)`
`x` または `init` の要素数に対して線形時間。 

- `multimap<Key,T,Compare,Allocator>& operator=(multimap<Key,T,Compare,Allocator>&& y)`
定数時間。


##例
```cpp
#include <iostream>
#include <map>
using namespace std;

int main()
{
  std::pair<int,char> values[] = { 
    std::make_pair(5,'e'), 
    std::make_pair(2,'b'), 
    std::make_pair(4,'d'), 
    std::make_pair(1,'a'),
    std::make_pair(1,'a'),
    std::make_pair(3,'c')
  };
  multimap<int, char> c1(values, values + 6);
  multimap<int, char> c2;

  c2 = c1;
  c1 = multimap<int,char>();

  cout << "Size of c1: " << c1.size() << endl;
  cout << "Size of c2: " << c2.size() << endl;

  return 0;
}

```

###出力
```
Size of c1: 0
Size of c2: 6
```

###処理系
- [Clang](/implementation#clang.md): ??
- [GCC](/implementation#gcc.md): ??
- [GCC, C++11 mode](/implementation#gcc.md): ??
- [ICC](/implementation#icc.md): ??
- [Visual C++](/implementation#visual_cpp.md): ??, 11.0


##参照

| 名前 | 説明 |
|---------------------------------------------------------------------------------------|-----------------------|
| [`insert`](/reference/map/multimap/insert.md) | 要素を挿入する |
| [`multimap`](/reference/map/multimap/multimap.md) | コンストラクタ |


