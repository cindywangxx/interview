
C++ 11引入的新特性 nonexcept


1 .作用：
nonexcept告诉编译器，函数不会发生异常，利于编译器对程序做更多优化。
如果在运行的时候nonexcept函数向外抛出了异常并且没有被捕捉到处理，程序会直接终止，调用std::terminate函数。阻止异常传播，提高安全性。

void swap(Type& x, Type& y) noexcept  //C++11
{
    x.swap(y);
}

2 .适用场合：
什么情况下推荐用nonexcept:
首推析构函数，析构函数抛出异常会带来不可预料的结果。C++11编译器中，析构函数默认是nonexcept的。
移动构造函数 move constructor
移动分配函数 move assignment
