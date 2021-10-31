### 判断一个字符是否是字母
```C++
cout << isalpha('a') << endl; // 1024  返回非0元素
cout << isalpha('5') << endl; // 0     返回0
cout << isalpha('D') << endl; // 1024  返回非0元素
```
### 判断一个字符是字母还是数字  a~z || A~Z || 0~9
```C++
cout << isalnum('a') << endl; // 8 返回非0元素
cout << isalnum('5') << endl; // 8 返回非0元素
cout << isalnum('D') << endl; // 8 返回非0元素
cout << isalnum('/') << endl; // 0 返回0
```
### 来判断一个字符是否为小写字母
```C++
cout << islower('a') << endl; // 512
cout << islower('2') << endl; // 0
cout << islower('A') << endl; // 0
```
### 判断一个字符是否为大写字母
```C++
cout << isupper('a') << endl; // 0
cout << isupper('2') << endl; // 0
cout << isupper('A') << endl; // 256
```
### 把字符转化为小写字母
```C++
cout << tolower('a') << endl; // 97
cout << tolower('2') << endl; // 50
cout << tolower('A') << endl; // 97
```
### 把字符转化为大写字母
```C++
cout << toupper('a') << endl; // 65
cout << toupper('2') << endl; // 50
cout << toupper('A') << endl; // 65
```