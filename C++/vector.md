### 构造函数初始化vector<string>
```C++
string str[]={"hello","world","hello","hello","world","hello","xyz","csl","edg","rng"};
int length = sizeof(str)/sizeof(string); // 10
vector<string> strArray(str, str+length);
```
### 使用arr[] 初始化 vector<int>
```C++
int arr[] = {0, 1, 0, 3, 12};
vector<int> vec(arr, arr + sizeof(arr)/sizeof(int));
```
### 初始化vector memo 为-1
```
int n = 10;
vector<int> memo(n + 1, -1);
cout << memo.size() << endl; // 11
```
