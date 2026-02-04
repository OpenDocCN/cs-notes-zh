# Classes

> 原文：[`courses.physics.illinois.edu/cs225/sp2019/notes/classes/`](https://courses.physics.illinois.edu/cs225/sp2019/notes/classes/)

返回笔记 by Eddie Huang

类对于汽车工厂就像对象对于汽车一样。类定义了某类对象的行为。它们包含属于类的变量和函数

## 描述矩形的类

```c
#include <iostream> using namespace std;

class Rectangle {
    int width, height;
  public:
    Rectangle ();
    Rectangle (int,int);
    int area (void) {return (width*height);}
};

Rectangle::Rectangle () {
  width = 5;
  height = 5;
}

Rectangle::Rectangle (int a, int b) {
  width = a;
  height = b;
} 
```

```c
int main () {
  Rectangle rect (3,4);
  Rectangle rectb;
  cout << "rect area: " << rect.area() << endl;
  cout << "rectb area: " << rectb.area() << endl;
  return 0;
} 
```

**输出**

```c
rect area: 12
rectb area: 30 
```
