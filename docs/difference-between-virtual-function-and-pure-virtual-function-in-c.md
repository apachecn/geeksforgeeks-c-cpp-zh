# c++ 中虚函数与纯虚函数的区别

> 原文:[https://www . geesforgeks . org/虚函数与纯虚函数的区别在 c/](https://www.geeksforgeeks.org/difference-between-virtual-function-and-pure-virtual-function-in-c/)

**[【c++ 中的虚函数】](https://www.geeksforgeeks.org/virtual-function-cpp/)**
虚函数是在基类中声明并由派生类重新定义(Overriden)的成员函数。当您使用指向基类的指针或引用来引用派生类对象时，您可以为该对象调用一个虚拟函数并执行该函数的派生类版本。

**[【c++ 中的纯虚函数】](https://www.geeksforgeeks.org/pure-virtual-functions-and-abstract-classes/)**
c++ 中的纯虚函数(或抽象函数)是我们没有实现的虚函数，我们只声明它。纯虚函数通过在声明中赋值 0 来声明。

**虚函数与纯虚函数的相似之处**

1.  这些是运行时多态性的概念。
2.  原型，即两个功能的声明在整个程序中保持不变。
3.  这些函数不能是全局的或静态的。

**c++ 中虚函数与纯虚函数的区别**

| 虚拟功能 | 纯虚函数 |
| --- | --- |
| 虚函数是基类的成员函数，可以由派生类重新定义。 | 纯虚函数是基类的成员函数，它唯一的声明是在基类中提供的，应该在派生类中定义，否则派生类也会变得抽象。 |
| 具有虚函数的类不是抽象的。 | 包含纯虚函数的基类变得抽象。 |
| 语法:

```cpp
virtual<func_type><func_name>()
{
    // code
}
```

 | 语法:

```cpp
virtual<func_type><func_name>()
    = 0;
```

 |
| 定义在基类中给出。 | 基类中没有给出定义。 |
| 具有虚函数的基类可以被实例化，即它的对象可以被制造。 | 具有纯虚函数的基类变得抽象，即它不能被实例化。 |
| 如果派生类不重新定义基类的虚函数，那么不影响编译。 | 如果派生类不重新定义基类的虚函数，那么没有编译错误，但是派生类也像基类一样变得抽象。 |
| 所有派生类都可以重新定义或不重新定义基类的虚函数。 | 所有的派生类必须重新定义基类的纯虚函数，否则派生类也会像基类一样变得抽象。 |