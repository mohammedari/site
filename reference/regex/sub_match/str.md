#str (C++11)
```cpp
string_type str() const;
```

##概要
マッチした文字列を `string_type` 型で返す。キャストと同じ。


##戻り値
`matched ? string_type(first, second) : string_type()`


##例
```cpp
#include <iostream>
#include <regex>

int main()
{
  const char s[] = "123";
  const std::regex re(R"(\d+)");
  std::cmatch m;
  if (std::regex_search(s, m, re)) {
    std::csub_match sub = m[0];
    if (sub.matched) {
      std::cout << '\'' << sub.str() << '\'' << std::endl;
      sub.matched = false;
      std::cout << '\'' << sub.str() << '\'' << std::endl;
    } else {
      std::cout << "not participate" << std::endl;
    }
  } else {
    std::cout << "not match" << std::endl;
  }
}
```
* str[color ff0000]
* iostream[link ../../iostream.md]
* regex[link ../../regex.md]
* cmatch[link ../match_results.md]
* regex_search[link ../regex_search.md]
* csub_match[link ../sub_match.md]

###出力
```
'123'
''
```


##バージョン
###言語
- C++11

###処理系
- [Clang](/implementation.md#clang): -
- [Clang, C++11 mode](/implementation.md#clang): 3.0, 3.1, 3.2, 3.3, 3.4, 3.5, 3.6
- [GCC](/implementation.md#gcc): -
- [GCC, C++11 mode](/implementation.md#gcc): 4.9.0, 4.9.1, 5.0.0
- [ICC](/implementation.md#icc): ??
- [Visual C++](/implementation.md#visual_cpp): ??