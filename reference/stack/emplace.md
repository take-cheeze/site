#emplace
```cpp
template <class... Args>void emplace(Args&&... args);
```

##概要
<b>要素型Tのコンストラクタ引数をとり、直接構築でスタックに要素を追加する。</b>


##効果
`c.emplace_back(std::[forward](/reference/utility/forward.md)<Args>(args)...);`

##戻り値
なし

##

##例
<pre style='margin-top:0px;margin-bottom:0px'><dfn/>```cpp
#include <iostream>
#include <stack>

struct MyObj
{
  MyObj(int i) { std::cout << i << " "; }
  MyObj(const MyObj&) { std::cout << "copy "; }
  MyObj(const MyObj&&) { std::cout << "move "; }
  MyObj& operator=(const MyObj&) { std::cout << "assign "; }
};

int main ()
{
  std::stack<MyObj> mystack;

  std::cout << "stack::push ";
  for (int i = 0; i < 5; ++i)
  {
    mystack.push(i);
  }
  std::cout << std::endl;

  std::cout << "stack::emplace ";
  for (int i = 0; i < 5; ++i)
  {
    mystack.emplace(i);
  }
  std::cout << std::endl;

  return 0;
}
</pre>
```

##出力
```cpp
<pre style='margin-top:0px;margin-bottom:0px;color:rgb(0,0,0);font-size:12px;line-height:normal'><samp>stack::push 0 copy 1 copy 2 copy 3 copy 4 copy
stack::emplace 0 1 2 3 4</samp></pre>
```

##参照
