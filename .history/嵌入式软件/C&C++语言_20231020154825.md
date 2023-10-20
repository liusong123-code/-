## C/C++语言
[toc]
### static关键字的作用
1. 在函数体，在函数调用的过程中维持值不变，只声明一次，延长变量的生命周期，经过static修饰的局部变量的地址存储在全局区；
2. 在函数体外，限定函数或者变量的作用域，表示只能在此文件中被使用；

### volatile关键字作用

* 作用：确保本条指令不会因编译器的优化而省略，且要求每次直接读值。
* 具体：
> 1. 保证对特殊地址的访问;
> 2. 到地址处读取;
> 3. 告诉编译器不要优化;
* 用处：
> 1. 在中断服务器中修改的变量;
> 2. 全局变量;
> 3. 多任务下各任务间的共享标志应该加volatile;

### inline作用

* 特性：用于实现的关键字（只有加在函数定义时才有用）
```C
inline int Max(int x, int y);//inline无用
inline int Max(int x, int y) //inline有用
{
   return (x > y)? x : y;
}
```
* inline只适合涵数体内代码简单的函数数使用；
* 内联是以代码膨胀（复制）为代价；
> 1. 如果函数体内的代码比较长，使用内联将导致内存消耗代价较高。
> 2. 如果函数体内出现循环，那么执行函数体内代码的时间要比函数调用的开销大。
###	 如何定义和使用函数指针
例子如下：
```C
#include <stdio.h>
 
int max(int x, int y)
{
    return x > y ? x : y;
}
 
int main(void)
{
    /* p 是函数指针 */
    int (* p)(int, int) = & max; // &可以省略
    int a, b, c, d;
    printf("请输入三个数字:");
    scanf("%d %d %d", & a, & b, & c);
    /* 与直接调用函数等价，d = max(max(a, b), c) */
    d = p(p(a, b), c); 
    printf("最大的数字是: %d\n", d);
    return 0;
}
```

###  已知地址如何存放数据
已知一个int类型的大内存地址

Int *p = （int*）0x123；
*p = 10；

typedef FUNC int（*fun）（int，int）
Int *p = (FUNC)0x123
P(p1,p2);






	进程之间通讯
A，	信号量
B，	消息队列
C，	管道
D，	套接字
E，	共享内存数据


	一年中有多少秒

#define YEAR_SECONDS 

	用宏求数组元素个数

#define ELEMENTS(A) (sizeof(A)/sizeof(A[0]))

	内存分配
堆区，栈区，全局区，常量区，代码区

  

