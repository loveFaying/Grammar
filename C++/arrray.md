### binary_search
```C++
int arr[]= {4,10,11,30,69,70,96,100};
int n = sizeof(arr)/sizeof(int);
int b = binary_search(arr, arr+n, 30); //查找成功，返回1
cout << "b:" << b << endl; // 1
int c = binary_search(arr, arr+n, 40); //查找失败，返回0
cout << "c:" << c << endl;
```
