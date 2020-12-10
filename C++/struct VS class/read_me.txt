C++ 中struct 和class的区别：
1）数据访问控制 
   struct是public的 class是private的。
   如果没有添加public/private修饰符，默认访问权限struct是public, class是private.
 
2）继承
   struct的默认继承是public的，而class是private的。

3）赋初值
   struct可以定义构造函数：
   
#include <iostream>
using namespace std;
struct A{
	int a;
	int b;
	A(int p1, int p2)
	{
		this->a = p1;
		this->b = p2; 
	}
}; 

int main()
{
	A test(2,3);
	std::cout << test.a << std::endl;
	return 0;
}

如果没有定义构造函数，可以用大括号给数据成员赋值。
A test = {2,3};

#include <iostream>
using namespace std;
struct A{
	int a;
	int b;
}; 

int main()
{
	A test = {2,3};
	std::cout << test.a << std::endl;
	return 0;
}

例外： 
A(): a(2), b(3) {} 这种构造模式定义下，不能用大括号进行赋值。 A test= {4,5} 会编译报错。

Class只有在全部数据成员变量都是public的情况下，才可以用大括号进行赋值。

 4）模板参数
 struct不能作为模板参数定义 
 template <strcut T> 编译报错
 只能: template <class T>
