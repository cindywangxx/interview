
#c++11 lamda

背景：
大量的小函数，只被一两处调用，不想费神去命名一个函数。那么就定义成匿名函数 lamda表达式。

格式：
[capture](param)opt->ret{body;}
1）capture 捕获列表 
   指可见域范围内lamda表达式代码内可见的参数。
   ex:
   [] 不捕获任何变量
   [=] 以值方式捕获当前作用域所有变量
   [&] 以引用方式捕获当前作用域所有变量
   [this]以值的方式捕获this指针, 捕获当前类中的 this 指针，让 lambda 表达式拥有和当前类成员函数同样的访问权限。捕获 this 的目的是可以在 lamda 中使用当前类的成员函数和成员变量。
   [a, &b] 文中定义的a以值方式捕获 b以引用方式捕获
2）param 参数列表
3）opt 函数选项
4）ret 返回值类型
5）body 函数体

eg: auto f = [](int i) -> int {return i+4;}
    std::cout << f(2) << std::endl;
    
NOTE: lamda表达式和auto的联合使用

1.在返回值非常明显的情况下，可以省略返回值的显示定义：
auto f = [](int i){return i+4;}  //编译器会自动推导出返回值类型
2.参数列表也是可以省略的
auto f = []{return 2;}




