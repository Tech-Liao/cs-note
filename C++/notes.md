# 侯捷C++高级编程课程

将构造函数放在private中，可以形成Singleton模式，就只有创建了一个对象。

在函数的**()**与**{}**之间加上const表示：函数不会改变数据。

```C++
class A
{
	double test() const {return x;}
	private:
		int x;
};
```

C++的引用在底层设计等于C语言的指针。const可以避免引用的修改。

## 友元

friend友元-指明某个函数或类通过对象访问对象的数据。相同类的对象互为友元。

## 返回引用

在返回值时，不能传函数内的局部变量的引用。

## 操作符重载

成员函数都会隐含：this指针。

### 成员函数的操作符重载

操作符重载，有两个操作数的操作符重载，都是将右边通过操作给左边。

this无法在函数中形式参数中指明，this指向调用者。

### 非成员函数的操作符重载

typename()--代表创建临时对象或临时变量

## 拷贝

### 拷贝构造

### 拷贝赋值

### 浅拷贝与深拷贝

浅拷贝：是指针拷贝，两个指针指向同一个内容

深拷贝：指的是内容拷贝，即两个对象指向两个内容，只是内容相同

## 析构函数

当对象有new的空间，在析构函数中，需要用delete释放new的空间





## static讨论

static可以用于函数和变量，形成静态变量和静态函数。类的内容存在内存中只有1份，不会根据对象个数的变动而变动。

静态成员函数没有this指针，即无法直接访问对象的数据，只能处理静态变量。

静态成员函数可以通过对象调用，也可以通过类名调用。

在非静态成员函数执行时，是根据**this**指针来判断执行的数据和内容。

## 模板

### 类模板

```c++
template<typename T>
class Test
{
private:
	T re,im;
};
//使用
Test<double> c1;
```

### 函数模板

```c++
template<class T>
const T& min(const T& a,const T& b)
{
    return b<a?b:a;
}
//使用
T r1,t2;
r3=min(r1,r2)	//编译器可以自行推导T，不需要写T
```

## namespace名字空间

```c++
namespace std	//将所有花括号内的东西都加上了std的名字。
{
};

//using directive直接使用名字空间
using namespace std;
//using declaration,仅使用某个空间的名字。
using std::cout
```





## 转换函数

转换函数没有返回类型，转换函数的type可以是任何类型，包括自定义类型

````c++
class Test
{
	operator double const{ return (double) xxx;}	//转换函数
}
````

## non-explicit-one-argument 构造函数

one-argument：需要1个实参。

explicit代表明确，表示必须显式的运用，才可以执行。
