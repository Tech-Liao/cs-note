# OOP

## 复合

```c++
class A;
class B
{
public:
	A x;
}
```

复合是指某个类中有其他类的对象，比如手机里有电池。

adapter形式：将某个功能强大的类A，再次改造成另一个类B，不修改A的内容。

### 析构与构造关系

构造函数从内到外执行（调用默认构造函数），析构函数由外到内执行。可以从现实中某个物品来理解，比如手机，先有电池，才可能有手机。先拆手机，才能拆电池。

## Delegation委托(composition by reference)

```c++
class A；
class B
{
private:
	A *rep;
};
```

作用：A的变动不会影响B，可当作编译防火墙。

## Inheritance继承

```c++
//表示B是A的子类。
class A;
class B:public A
{
};
```

继承有三种形式：public，private，protected。

父类的数据被子类继承。父类的析构函数必须是virtual。

## 虚函数

```C++
virtual void test() const =0; //纯虚函数
virtual void error(const double &x);	//常见虚函数 
```

虚函数：指父类声明或定义的函数，希望子类重新定义（重载）该函数。

纯虚函数：父类只是声明了函数，并未定义，子类必须重新定义。