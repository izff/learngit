## coding笔记
---
### 语言分类：强弱、动态及静态

1. Program errors: 
	* trapped errors: 程序终止；除以0，java的数组越界；
	* untrapped errors: 出错后继续执行；如C语言中的缓存区溢出，jump到错误地址。

2. Forbidden behavior: 必须包含所有untrapped error，包含部分trapped error。

3. Well behaved: 程序执行不可能出现forbidden behaviors；与之相对的有，Ill behaved。

5. 强类型（strongly）：所有程序均well behaved；否则为weakly typed。比如C语言的缓冲区溢出，属于trapped errors，即属于forbidden behavior，故C是弱类型。

6. 静态类型 statically: 如果在编译时拒绝ill behaved程序，则是statically typed;
动态类型dynamiclly: 如果在运行时拒绝ill behaviors, 则是dynamiclly typed。

7. 具体列表：
	* 无类型： 汇编
	* 弱类型、静态类型 ： C/C++
	* 弱类型、动态类型检查： Perl/PHP
	* 强类型、静态类型检查 ：Java/C#
	* 强类型、动态类型检查 ：Python, Scheme
	* 静态显式类型 ：Java/C
	* 静态隐式类型 ：Ocaml, Haskell

--	
### Java数据抽象

1. 抽象数据类型 和 静态方法库

2. 对象：
	* 状态（数据类型中的值）
	* 标志（将一个对象区别于另一个，相当于内存中的位置）
	* 行为（对数据类型的操作）
	
	引用：访问对象的一种方式，可以认为就是内存地址。

3. 静态方法：主要作用是实现函数；非静态（实例）方法：实现数据类型的操作。静态方法的调用开头是类名（按习惯大写），非静态方法的开头总是对象（实例）名，按习惯小写。

4. 数据类型：一组值和一组对值的操作的集合。

--
### Java 自动装箱和拆箱

1. 数据类型分类：
	基本类型并不及继承于公共基类Object，引用类型却是。因此，基本类型没办法直接添加到一个ArrayList的对象列表中。
	1. 基本类型 primitive type：boolean类型 和 数值类型（byte, int, float, double etc.）也叫原始数据类型；
	2. 引用类型 reference type：空类型，数组，接口，类。

2. 要将数值添加到 ArrayList 中，需要先将数值包装在封装器类（一种引用类型）里面，如Integer，Double，Boolean这些。

3. 所有基本类型（包括void）的包装类都使用了final修饰，因此我们无法继承它们扩展新的类，也无法重写它们的任何方法。

4. Java 1.5 中引入了一个新特性：自动装箱/拆箱（auto boxing/unboxing）。
	第二行中，基本类型自动装箱成 Integel，然后加入 Object 类型的列表中；第三行，Object 列表中取出元素，现自动转为Integer，然后拆箱变成基本类型的 int 。

``` java
ArrayList list = new ArrayList();
list.add(5); // auto boxing
int i = (Integer)list.get(0); // auto unboxing
```

### 生存分析 与 Kaplan-Meier 估算子

--
### 正态分布的置信区间

* （1）sigma已知时mu的置信区间

	mu的点估计为样本x的平均值，分布为 N(<x>, sigma^2/n) (中心极限定理)
	![](figs/confidencelevel-1.png)
	易知：
	![](figs/confidencelevel-2.png)

* （2）sigma未知时mu的置信区间

	![](figs/confidencelevel-3.png)

* （3）sigma的置信区间
	
	![](figs/confidencelevel-4.png)
	![](figs/confidencelevel-5.png)
	
