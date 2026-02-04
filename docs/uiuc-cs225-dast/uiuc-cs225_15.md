# 模板

> 原文：[`courses.physics.illinois.edu/cs225/sp2019/notes/templates/`](https://courses.physics.illinois.edu/cs225/sp2019/notes/templates/)

返回笔记 —— 由黄艾迪编写

模板可以帮助你使函数和类在不同数据类型上更加灵活

## 两个项目最大值的函数模板

```c
#include <iostream> using namespace std;

template <class T>
T GetMax (T a, T b) {
  T result;
  result = (a>b)? a : b;
  return (result);
} 
```

```c
int main () {
  int i=5, j=6, k;
  long l=10, m=5, n;
  k=GetMax<int>(i,j);
  n=GetMax<long>(l,m);
  cout << k << endl;
  cout << n << endl;
  return 0;
} 
```

**输出**

```c
6
10 
```

## 项目的成对模板

```c
// class templates
#include <iostream> using namespace std;

template <class T>
class mypair {
    T a, b;
  public:
    mypair (T first, T second)
      {a=first; b=second;}
    T getmax ();
};

template <class T>
T mypair<T>::getmax ()
{
  T retval;
  retval = a>b? a : b;
  return retval;
} 
```

```c
int main () {
  mypair <int> myobject (100, 75);
  cout << myobject.getmax();
  return 0;
} 
```

**输出**

```c
100 
```
