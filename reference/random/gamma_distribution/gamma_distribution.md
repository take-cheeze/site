#コンストラクタ(C++11)
```cpp
explicit gamma_distribution(RealType alpha = 1.0, RealType beta = 1.0);
explicit gamma_distribution(const param_type& parm);
```

##`gamma_distribution`オブジェクトの構築
- `explicit gamma_distribution(RealType alpha = 1.0, RealType beta = 1.0);`

値を生成する範囲として形状母数`alpha`および尺度母数`beta`を受け取るコンストラクタ。 

要件： `a > 0`かつ`b > 0`であること。


- `explicit gamma_distribution(const param_type& parm);`

パラメータオブジェクトを受け取るコンストラクタ。`param_type`は、このクラスのコンストラクタと同じオーバーロードを持ち、それらのコンストラクタのパラメータを保持している。このコンストラクタでは、`param`オブジェクトが持っているパラメータを、このクラスのコンストラクタに転送する。 


##例
```cpp
#include <iostream>
#include <random>

int main() 
{
  std::random_device seed_gen;
  std::default_random_engine engine(seed_gen());

  // パラメータを個別に指定する
  {
    // 形状母数1.0、尺度母数1.0で分布させる
    std::gamma_distribution<> dist(1.0, 1.0);

    for (int i = 0; i < 10; ++i) {
      std::cout << dist(engine) << " ";
    }
  }
  std::cout << std::endl;

  // パラメータを通して範囲指定する
  {
    typedef std::gamma_distribution<> dist_type;

    // 形状母数1.0、尺度母数1.0で分布させる
    dist_type::param_type param(1.0, 1.0);
    dist_type dist(param);

    for (int i = 0; i < 10; ++i) {
      std::cout << dist(engine) << " ";
    }
  }
}
```


###出力例
```
0.365864 2.62428 2.2892 2.88907 0.159108 0.811572 0.639582 0.0461815 0.0372937 0.391902 
1.51719 0.10519 0.856907 2.47365 2.23435 1.01822 3.01892 1.10875 2.20858 3.91652 
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


