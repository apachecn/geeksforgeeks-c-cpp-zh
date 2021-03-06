# 型铸造与型转换的区别

> 原文:[https://www . geesforgeks . org/type-casting 和-type-conversion 的区别/](https://www.geeksforgeeks.org/difference-between-type-casting-and-type-conversion/)

**1。类型转换:**
在类型转换中，程序员在程序设计过程中使用转换运算符将一种数据类型转换为另一种数据类型。在类型转换中，当将数据类型转换为另一种数据类型时，目标数据类型可能小于源数据类型，这就是为什么它也被称为收缩转换。

**语法/声明:-**

```cpp
destination_datatype = (target_datatype)variable;

(): is a casting operator.
```

**target_datatype:** 是我们要转换源数据类型的数据类型。

**型铸造示例–**

```cpp
float x;
byte y;
...
...
y=(byte)x;  //Line 5 
```

**在第 5 行:**可以看到，我们正在将**浮点(源)数据类型**转换为**字节(目标)数据类型**。

**2。类型转换:**
在类型转换中，编译器会在编译时自动将一种数据类型转换为另一种数据类型。在类型转换中，目标数据类型不能小于源数据类型，这就是为什么它也被称为扩展转换。更重要的是，它只能应用于兼容的数据类型。

**类型转换示例–**

```cpp
int x=30;
float y;
y=x;  // y==30.000000\. 
```

让我们看看下面给出的类型转换和类型转换之间的区别:

| S.NO | 类型铸造 | 类型变换 |
| --- | --- | --- |
| 1. | 在类型转换中，程序员使用转换运算符将一种数据类型转换为另一种数据类型。 | 而在类型转换中，一个数据类型被编译器转换成另一个数据类型。 |
| 2. | 类型转换可以应用于**兼容数据类型**以及**不兼容数据类型**。 | 而类型转换只能应用于**兼容的数据类型**。 |
| 3. | 在类型转换中，需要转换运算符来将一个数据类型转换为另一个数据类型。 | 而在类型转换中，不需要转换操作符。 |
| 4. | 在类型转换中，当将数据类型转换为另一种数据类型时，目标数据类型可能小于源数据类型。 | 而在类型转换中，目标数据类型不能小于源数据类型。 |
| 5. | 类型转换发生在程序员设计程序的过程中。 | 而类型转换是在编译时完成的。 |
| 6. | 类型转换也称为收缩转换，因为在这种情况下，目标数据类型可能小于源数据类型。 | 而类型转换也称为扩展转换，因为在这种情况下，目标数据类型不能小于源数据类型。 |
| 7. | 类型转换经常用于编码和竞争性编程工作中。 | 而类型转换在编码和竞争性编程中使用较少，因为它可能导致不正确的答案。 |
| 8. | 型铸造更高效可靠。 | 而类型转换效率较低，可靠性较低。 |