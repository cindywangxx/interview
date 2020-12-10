
# content about c++11 auto

用于type reduce

作用：
1.声明变量的时候根据初始值判断对象类型。因此！！！不接受没有初始值的变量声明！
auto y; //编译会报错
auto z = new auto(8) //z 是int型指针

同理，函数和模板参数不能被声明为auto.

2.用于容器的迭代 iterator
std::vector<int> test;
std::vector<int>::interator iter = test.begin();//method 1
auto i = test.begin; //method 2 , 让STL变得更简洁

3. 配合lamda表达式一起用???




