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
```C++
int n = 10;
vector<int> memo(n + 1, -1);
cout << memo.size() << endl; // 11
```
### 输出vector<int>
```C++
void printVector(vector<int>& arr){
    for (auto val : arr)
        cout << val << " ";
    cout << endl;
} 
```
### 对vector<int>进行排序、输出最大值最小值、最大值最小值在数组中的位置
```C++
int arr[] = {1,3,5,7,9,8,6,4,2,0};
int n = sizeof(arr)/sizeof(int);

vector<int> vec(arr, arr+n);
sort(vec.begin(), vec.end()); // 从小到大
sort(vec.begin(), vec.end(), greater<>()); // 从大到小
vector<int>::iterator biggest = max_element(begin(vec), end(vec));
auto smallest = min_element(vec.begin(), vec.end());
cout << *biggest << " " << *smallest << " " << endl;
cout << distance(vec.begin(), biggest) << " " << distance(vec.begin(), smallest) << endl;
```
