# c++ STL 中的无序 _ 映射 get _ 分配器

> 原文:[https://www . geesforgeks . org/unordered _ map-get _ 分配器-in-c-stl/](https://www.geeksforgeeks.org/unordered_map-get_allocator-in-c-stl/)

**[【无序 _ 映射】](https://www.geeksforgeeks.org/unordered_map-in-stl-and-its-applications/):get _ 分配器()**是 C++ STL 中的内置函数，用于获取容器无序 _ 映射的分配器。
**语法**

```
Allocator_type get_allocator()

```

**参数:**此功能不接受任何参数。
**返回值:**返回一个与无序 _map 关联的分配器。

下面的程序清楚地解释了**无序 _ 映射::get _ 分配器()**函数。
**例-1:**

```
// CPP program to illustrate
// unordered_map get_allocator()
#include <bits/stdc++.h>
using namespace std;

int main()
{

    //'ump' is object of 'unordered_ump'
    unordered_map<int, int> ump;

    //'allocator_type' is inherit in 'unordered_map'
    //'u' is object of 'allocator_type'
    unordered_map<int, int>::allocator_type u = ump.get_allocator();

    // Comparing the Allocator with Pair<int, int>
    cout << "Is allocator Pair<int, int> : "
         << boolalpha
         << (u == allocator<pair<int, int> >());

    return 0;
}
```

**Output:**

```
Is allocator Pair : true 
```

**示例-2:**

```
// CPP program to illustrate
// unordered_map get_allocator()
#include <bits/stdc++.h>
using namespace std;

int main(void)
{
    unordered_map<char, int> um;
    pair<const char, int>* a;

    a = um.get_allocator().allocate(8);

    cout << "Allocated size = " << sizeof(*a) * 8 << endl;

    return 0;
}
```

**Output:**

```
Allocated size = 64

```