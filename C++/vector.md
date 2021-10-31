### 构造函数初始化vector\<string\>
```C++
string str[]={"hello","world","hello","hello","world","hello","xyz","csl","edg","rng"};
int length = sizeof(str)/sizeof(string); // 10
vector<string> strArray(str, str+length);

vector<string> vec{"houyw", "houyw2", "houyw3"};
vector<int> vec2{1,2,3,4};
```
### 使用arr[] 初始化 vector\<int\>
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
### 输出vector\<int\>
```C++
// 方法1
void printVector(vector<int>& arr){
    for (auto val : arr)
        cout << val << " "; // val是arr中的每个元素
    cout << endl;
}
// 如果需要改变容器中的值需要加上引用
vector<int> arr;
for(auto& n: arr)  // 只遍历不修改 const auto& n: arr
	cout << n++ << " ";

// 方法2
void MyPrint(int val){
    cout << val << " ";
}
for_each(vec.begin(), vec.end(), MyPrint);
```
### 对vector\<int\>进行排序、输出最大值最小值、最大值最小值在数组中的位置
```C++
int arr[] = {1,3,5,7,9,8,6,4,2,0};
int n = sizeof(arr)/sizeof(int);

vector<int> vec(arr, arr+n);
sort(vec.begin(), vec.end()); // 从小到大
sort(vec.begin(), vec.end(), greater<>()); // 从大到小
vector<int>::iterator biggest = max_element(begin(vec), end(vec)); // 9 0
auto smallest = min_element(vec.begin(), vec.end()); // 0 9
cout << *biggest << " " << *smallest << " " << endl;
cout << distance(vec.begin(), biggest) << " " << distance(vec.begin(), smallest) << endl;
```
### 对vector\<int\>进行二分查找
```C++
int arr[]= {4,10,11,30,69,70,96,100};
int n = sizeof(arr)/sizeof(int);
vector<int> vec(arr, arr+n);
if ( binary_search(vec.begin(), vec.end(), 100) )
    cout << "Yes" << endl;
else 
    cout << "No" << endl;
```
### vector< vector\<int\> > v
```C++
vector< vector<int> >  v;

vector<int> v1;
vector<int> v2;
vector<int> v3;
vector<int> v4;

for (int i = 0; i < 4; i++) {
    v1.push_back(i + 1);
    v2.push_back(i + 2);
    v3.push_back(i + 3);
    v4.push_back(i + 4);
}

//将容器元素插入到vector v中
v.push_back(v1);
v.push_back(v2);
v.push_back(v3);
v.push_back(v4);

for (vector<vector<int>>::iterator it = v.begin(); it != v.end(); it++) {

    for (vector<int>::iterator vit = (*it).begin(); vit != (*it).end(); vit++) {
        cout << *vit << " ";
    }
    cout << endl;
}
```
### 统计vector\<int\>中指定元素的个数
```C++
vector<int> v;
v.push_back(1);
v.push_back(2);
v.push_back(4);
v.push_back(5);
v.push_back(3);
v.push_back(4);
v.push_back(4);

int num = count(v.begin(), v.end(), 4);

cout << "4的个数为： " << num << endl;
```
### 按照条件统计元素的个数
```C++
class Greater4
{
public:
	bool operator()(int val)
	{
		return val >= 4;
	}
};
// 大于4元素的个数
int num = count_if(v.begin(), v.end(), Greater4()); 
```
### 将vector\<int\>反转、替换
```C++
vector<int> v;
reverse(v.begin(), v.end());
replace(v.begin(), v.end(), 20,2000); // 将v中的元素20替换成2000
```
### 将vector\<int\> 进行条件替换
```C++
class ReplaceGreater30
{
public:
	bool operator()(int val)
	{
		return val >= 30;
	}

};
//将容器中大于等于的30 替换成 3000
replace_if(v.begin(), v.end(), ReplaceGreater30(), 3000);
```
### emplace_back
简而言之，emplace_back()是C11标准中的函数，用法和功能与push_back一样，执行效率比push_back高。
```C++
vector<string> res;
res.push_back(word);
res.emplace_back(word);
```
