// some contents about C++ "const"

1：使用方法
1-1：定义常量  
常量值不可改变
eg: const int a = 12;

默认情况下const定义的常量只可以在本文件使用，改为外部连接会扩展到全局，其它文件也可以使用： ？？
extend const int a; 

1-2：const指针
1）指针本身是常量不可变
int * const test_ptr;
2) 指针指向的变量是常量不可变
const int * test_ptr;
3) 两者都不可变
const int * const test_ptr;

判断方法: 沿着* 左右区分，左边就是指向常量，右边就是指针常量。

1-2：const修饰函数
1）传递进来的形参在函数内不可以改变
void func(const int index) //index在函数内不能改变
本来index就是临时变量，复制的实参，所以无意义。

2）参数指针所指内容为常量不可变
void func(const int * p)

3) 参数指针本身为常量不可变
void func（int * const p）

4) 参数为引用，增加效率的同时防止更改
自定义类型的参数传递，需要临时对象复制参数，对于临时对象的构造，需要调用构造函数，比较浪费时间，因此我们采取 const 外加引用传递的方法。
void func(const int& index)
对于一般的 int double 类型数据 不用引用传递。














