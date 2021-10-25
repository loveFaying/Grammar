### 构造函数初始化vector<string>
```C++
string str[]={"hello","world","hello","hello","world","hello","xyz","csl","edg","rng"};
int length = sizeof(str)/sizeof(string); // 10
vector<string> strArray(str, str+length);
```
