### 输出map
```C++
map<string, int> myMap;
for(auto it = myMap.begin() ; it != myMap.end() ; it ++)
	cout << it->first << "->" << it->second << endl;

for(auto val: myMap)
	cout << val.first << "->" << val.second << endl; //pair
```
### 统计vector\<int\>& nums中每个元素出现的次数
```C++
unordered_map<int, int> myMap;
for (int num: nums) {
	myMap[num]++;
}

for (const auto& val: myMap) { // 不修改myMap
	cout << val.first << "->" << val.second << endl;
}
```
