# 如何在开关块内部处理语句，但在外壳外部处理语句

> 原文:[https://www . geeksforgeeks . org/如何在开关内部处理语句块但在外壳外部/](https://www.geeksforgeeks.org/how-a-statement-is-handled-inside-switch-block-but-outside-case/)

[Switch](https://www.geeksforgeeks.org/switch-statement-cc/) case 语句是将一个变量与几个整数值进行比较的长 if 语句的替代语句。switch 语句是一个多路分支语句。它提供了一种简单的方法，可以根据表达式的值将执行分派到代码的不同部分。它是一个控制语句，允许一个值改变对执行的控制。

**语法:**

## C++

```cpp
// Syntax for Switch Case
switch (n) {

// code to be executed if n = 1
case 1:
    break;

// code to be executed if n = 2
case 2:
    break;

// code to be executed if n
// doesn't match any cases
default:
}
```

**要点:**

1.  Switch 接受输入参数并选择一个案例。
2.  在这种情况下使用的表达式应该是常量类型。
3.  **任何情况之外的语句都不会被执行。**

本文重点讨论第三条语句“任何情况之外的语句都不会被执行”。

**例 1:** 预测以下程序的输出:

## C

```cpp
// C program to illustrate the switch statement
#include <stdio.h>

// Driver Code
int main()
{
    switch (1) {
        int test = 10;
        printf("dead code\n");
    case 1:
        printf("%d\n", test);
    }

    return 0;
}
```

**Output:**

> Zero

**说明:**即使测试的值假设为 10，也获得垃圾值作为输出。可以清楚地看到，案例 1 之前的 print 语句被忽略(可能在[代码优化](https://www.geeksforgeeks.org/code-optimization-in-compiler-design/)期间作为死代码消除的一部分被移除)，因此可以得出结论，前面的语句也没有被执行。意思是**变量测试**没有申报。是真的吗？让我们看看。

**分析器和符号表:** [词法分析](https://www.geeksforgeeks.org/introduction-of-lexical-analysis/)是编译器的第一阶段，也称为扫描器或分析器。它将高级输入程序转换成一系列令牌。这些令牌可以是不同类型的。[符号表](https://www.geeksforgeeks.org/symbol-table-compiler/)是由编译器创建和维护的数据结构。它存储关于范围的信息和关于名称的绑定信息，关于各种实体实例的信息，例如变量和函数名、类、对象等。

符号表中有许多列，但为了简单起见，让我们采用“变量名”和“地址”字段。

**例 1:**int x = 5；

> **词法分析器:**
> int–关键字
> x–标识符
> =–运算符
> 5–常量
> ；–特殊符号
> 
> **符号表:**
> ———————————————————
> |变量名|地址|
> ———————————————
> | x | 0 |
> —————————————————————————————————————————————————————————————————————

**例 2:**

> void main(int a)
> {
> int b = a；
> 
> **词法分析器:**
> 
> void-关键字
> main–标识符
> ()–特殊符号
> { }–特殊符号
> int–关键字
> a–标识符
> b–标识符
> =–运算符
> ；–特殊符号
> 
> **符号表-**T2】—————————
> |变量名|地址|
> ————————————————
> |主| 0 |
> ——————————————————————————————————
> | a | 4 |
> ——————————————————————————————————————

如果没有执行 Case 之外的语句，怎么可能在不声明的情况下使用变量‘test’？让我们看看这一行是如何绕过编译的分析阶段的。

**<u>词法分析器</u> :** Lexer 会正常解析整个程序。这是创建符号表的阶段，变量**测试**因此被识别为令牌并添加到符号表中。

> ——————————————————————
> |变量名|地址|
> ——————————————————————
> |测试| 0 |
> ——————————————————————

**<u>语法分析器</u> :** 查看整个程序的语法。从结构上来说，我们的程序非常好。到目前为止没有错误。

**<u>语义分析器</u> :** 它会尝试给解析树赋予意义。变量**测试**被指定为整数类型，并已成功绕过所有分析阶段。

> ———————————————————“T0”|变量名称|地址|类型|
> —————————————————————“T2”|测试| 0 | int |
> ———————————————————————————————————————————————————————————————————————————————

现在标识符**测试**已经成功占据了符号表中的一个位置。符号表在运行时用值填充，但是因为在运行时第 5 行和第 6 行没有被执行，所以变量测试的值没有被更新。因此我们得到一些垃圾值作为输出。