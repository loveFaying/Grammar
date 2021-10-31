### 找子串第一次出现的位置和最后一次出现的位置
```C++
//查找
string str1 = "abcdefgde";
int pos = str1.find("de");
if (pos == -1)
	cout << "未找到" << endl;
else
	cout << "pos = " << pos << endl;
pos = str1.rfind("de"); // "de"最后一次出现的位置(从右往左第一次出现的位置)
cout << "pos = " << pos << endl;
/*
pos = 3
pos = 7
*/
```
