---
title: python字串符、元组和列表语法
id: 2001
date: 2019-06-30 11:28:10
tags:
- python  
permalink: 2001        

categories: 
  - 笔记本
---
python列表(list)列表是处理一组有序项目的数据结构，即可以在列表中存储一个序列的项目
列表是可变的数据结构，处理数据更加灵活。列表以中括号定义
<!--more-->
后面的内容在首页不显示，只显示到<!--more-->这里


---
title: python字串符、元组和列表语法
id: 2001
date: 2019-06-30 11:28:10
tags:
- python  
permalink: 2001        

categories: 
  - 笔记本
---
python列表(list)列表是处理一组有序项目的数据结构，即可以在列表中存储一个序列的项目
列表是可变的数据结构，处理数据更加灵活
列表以中括号定义
列表定义
<!--more-->
后面的内容在首页不显示，只显示到<!--more-->这里


##python数值和字符串
###数值类型
###整数类型 int
整数类型范围是2的32次方，这个数量是从-2147483648 到 2147483648，一共4294967296个数值
```python
In [1]: y =1 
In [2]: y 
Out[2]: 1
In [3]: type(y) 
Out[3]: int
In [4]: 2 ** 32 
Out[4]: 4294967296
```
###长整数类型  long
数值比较大的类型，python会进行缩进显示，缩进后面会使用L表示，类型为long。在python3特性中，比较大的数值也是int类型
```ipython
In [2]: y
Out[2]: 9999999999999999999999999999999999999999L
In [3]: type (y)
Out[3]: long

In [6]: y
Out[6]: 999999999999999999999999999999999999
In [7]: type (y) 
Out[7]: int
```
###浮点数类型  float
变量或数值运算中，只要有一个数值带有浮点符号或者浮点运算的类型(比如2的5次方，表示为2e+5，结果会以浮点数显示)。浮点数类型为float
次方运算
```ipython
In [1]: 2e+5 
Out[1]: 200000.0
In [2]: type(2e+5) 
Out[2]: float
```
###浮点运算
```python
In [3]: 7/2.3 
Out[3]: 3.0434782608695654
In [4]: 7.0/2 
Out[4]: 3.5
```
###复数类型 complex
复数是由一个实数和一个虚数组合构成，表示为：x+yj
一个负数时一对有序浮点数(x,y)，其中x是实数部分，y是虚数部分。
Python语言中有关负数的概念：
```shell
1、虚数不能单独存在，它们总是和一个值为0.0的实数部分一起构成一个复数 
2、复数由实数部分和虚数部分构成 
3、表示虚数的语法：real+imagej 
4、实数部分和虚数部分都是浮点数 
5、虚数部分必须有后缀j或J 
复数的内建属性： 
复数对象拥有数据属性，分别为该复数的实部和虚部。 
复数还拥有conjugate方法，调用它可以返回该复数的共轭复数对象。 
复数属性：real(复数的实部)、imag(复数的虚部)、conjugate()（返回复数的共轭复数） 
```
###复数的赋值与共轭
```python
In [1]: a=5.6+3.222j

In [2]: a
Out[2]: (5.6+3.222j)
```
###取值复数的实数部分
```python
In [3]: print (a.real)
5.6
```
###取值复数的虚数部分
```python
In [4]: print (a.imag)
3.222
```
###字符串的类型
字符串 str
字符串有三种引号模式，其中有单引号、双引号和三引号，三引号必须是连续相同的引号。这三种引号同样表示赋值字串符
```python
In [19]: y = '123'
In [20]: type (y)
Out[20]: str
In [21]: y = "123"
In [22]: type (y)
Out[22]: str
In [23]: y = '''123'''
In [24]: type (y)
Out[24]: str
```
三引号出了赋值字串符外还有注释的功能，将内容的某一段进行注释。在变量引用中也可以代替\n的换行符
三引号注释内容，命令行中会输出显示，文件中则不会，因为代表注释内容
```python
In [25]: '''hello world!'''
Out[25]: 'hello world!'
```
三引号换行输出
```python
In [30]: y = '''hello
   ...: wrold! '''
In [31]: print y
hello
wrold!
```
###索引与切片操作
字符串切片取值操作
定义y变量，变量中指定的是字符串值，切片根据字符串位来取值，比如取值一个字符串变量的第一个到第三个(切片位数是从0开始的，计算机计数基本上都是从0位开始计数)。而python切片从0位开始(可以通过切片测试发现切片0返回的结果是字符串1，切片1返回的结果是字符串2)
定义字串符变量y
```python
In [5]: y = '123456'
In [6]: y [1]
Out[6]: '2'
取值0到3位
In [7]: y [0:3]
Out[7]: '123'
切片从0开始取值
In [2]: y [0]
Out[2]: '1'
In [3]: y [1]
Out[3]: '2'
```
###字符串索引
字符串索引时0表示开始时的值，索引到结束时的值需要+1，如取出abc两个字符表示[0:3]
```python
In [4]: x = 'abcdefg'

In [5]: x [0:2]
Out[5]: 'ab'

In [6]: x [0:3]
Out[6]: 'abc'
```
-1表示切片取值字符串中最后一个字符，这里返回结果是g
```python
In [7]: x [-1]
Out[7]: 'g'
```
:表示省去左边的引索匹配(相同于省略写0)，后面跟整数表示取出多少个字符串，不写整数只用:表示，则表示取值所有字符串
```python
In [10]: x [:3]
Out[10]: 'abc'

In [11]: x [:]
Out[11]: 'abcdefg'
```
:冒号左边跟整数表示省略左边的多少个字符，冒号右边不跟整数表示取出所有，正整数和负整数表达的结果基本一致。
```python
In [12]: x [2:]
Out[12]: 'cdefg'

In [13]: x [5:]
Out[13]: 'fg'
```
:冒号左边跟整数表示省略左边的多少个字符，右边不跟负整数表示取出所有，这里负整数倒叙，这里最大取值-1，如果想取出开始位到后面所有的字符串，则后面不跟任何切片数值
```python
In [25]: x [3:-1]
Out[25]: 'def'

In [26]: x [3:]
Out[26]: 'defg'
 
In [30]: x [-5:-1]
Out[30]: 'cdef'
```
e表示在字符中是倒数第三位，用-3表示。a在变量中是倒数第八位(实际为-7位，最后一个结束字符+1位表达)，用-8表示。取值范围: g[fedbca]，最后一个-1表示倒叙取值
```python
In [31]:x [-3:-8:-1]
Out[31]: 'edcba'
   gfedcba
```
双冒号表示步长值，每隔两步取一个值，双冒号表示取值位是1，从变量开始位来取值，另如从变量第二位开始取值
```python
In [48]: x[::2]
Out[48]: 'aceg'
```
从第二位取值，跳过将a切片取值 
```python
In [50]: x[2::2]
Out[50]: 'ceg
```
倒叙的从右往左取值，每隔两步取出一个字符串
```python
In [53]: b[::-2] 
Out[53]: 'eca'
```
##python字符串
字串符、元组都是序列，字符串和元组都是不可变序列
序列的两个主要特点是引索操作、符合切片操作
索引操作符让我们从序列中抓取一个特定的字符项目
切片操作符让我们能获取序列中的一个切片，即一部分序列
```python
len()      求序列长度，len字符序列统计长度不能针对int类型
+          连接两个序列。字符串和int整数类型不能使用+相连
*          在数值类型中是乘运算，在字符串中则是重复序列元素
in         判断元素是否在一个序列中，比如判断a字符是否在这个y的序列中，返回结果为true和falsh结果
max()      返回最大值
min()      返回最小值
cmp(x,y)   比较两个序列是否相等 
len()      求序列长度
```
```python
In [5]: x = 'qerasd'

In [6]: len(x)
Out[6]: 6
```
###连接两个序列(字符串)
```python
In [8]: y = '123456'

In [9]: y + x
Out[9]: '123456qerasd'
```
###重复序列元素
int类型是相乘，字符串则是重复，如y是字符串，a是int整数类型
```python
In [10]: y * 10
Out[10]: '123456123456123456123456123456123456123456123456123456123456'

In [11]: a = 123

In [12]: a * 10
Out[12]: 1230
```
###判断一个字符是否在序列中
返回结果true和falsh，如果有返回true，没有返回falsh
```python
In [17]: 'j' in x
Out[17]: False

In [18]: 'q' in x
Out[18]: True

In [19]: x
Out[19]: 'qerasd'
```
###取值字符串序列中最大值和最小值(数字和字母排序)
比如y字符串是123456，去最小值1和最大值6
```python
In [24]: min (y)
Out[24]: '1'

In [25]: max (y)
Out[25]: '6'
```
###cmp方法
比较两个序列是否相同或一致，比如h字符串序列是qwerty，如果相同返回0，1表示后面的字符大于前面(h序列)，-1前面(h序列)小于后面
```python
In [37]: cmp(h,'qwerty')
Out[37]: 0

In [38]: cmp(h,'qwert')
Out[38]: 1

In [39]: cmp(h,'qwertya')
Out[39]: -1
```
##元组
```shell
元组与列表十分相似
元组与字串符一样是不可变的
元组内的元素以逗号分隔
元组可以存储字符串、数值、另外的元组
-元组可以存储一系列的值
-元组通常用在用户定义函数能够安全地采用一组值得时候，即被使用元组的值不会改变
定义一个元组数值，a是之前表达出的变量
```
###定义一个元组，元组里可以定义另外的一个元组，元组通常接收函数的返回值
```python
In [41]: t
Out[41]: ('y', 1, ('qerasd', 1))

In [42]: type (t)
Out[42]: tuple

如果定义一个元组时，元组内的元素必须添加,号来表示，否则定义的元组元素则会改变属性，比如数字是int类型、字母则是str类型，定义一个元组元素时必须指定一个逗号，如
In [43]: yl = (1)

In [44]: type (yl)
Out[44]: int

In [45]: yl = (1,)

In [46]: type (yl)
Out[46]: tuple
```
###元组定义多个元素或多个元组相连，如t元组加上tl元组键入到yl的元组中，yl元组则可以将两个元组相连
```python
In [59]: t
Out[59]: ('y', 1, ('qerasd', 1))

In [60]: tl
Out[60]: ('x', 54)

In [61]: yl = (t,tl)

In [62]: yl
Out[62]: (('y', 1, ('qerasd', 1)), ('x', 54))
```
###元组不可变，不能通过指定序列位来改变元素内容，比如修改yl中的元素则会返回异常
```python
In [65]: yl[3] = 3
---------------------------------------------------------------------------
TypeError Traceback (most recent call last)
<ipython-input-65-c8a7acc9ac79> in <module>()
----> 1 yl[3] = 3

TypeError: 'tuple' object does not support item assignment

```
###定义元组相连变量和字符串的元素值，元组内不添加单引号的表示是一个变量，比如现有变量a = 123
```python
In [67]: yl = (a,'d','c')

In [68]: yl
Out[68]: (123, 'd', 'c')
```
###元组的拆分
一个元组内如果有多个元素，且元素需要单独重新引用，可将元组内的元素转为变量，比如将上述的yl元组的三个元素赋值给三个变量(通常元组用于函数的返回值的定义)
```python
In [70]: y1,y2,y3 = yl

In [71]: y1
Out[71]: 123

In [72]: y2
Out[72]: 'd'

In [73]: y3
Out[73]: 'c'
```
###获取元组(tuple)的python内置使用方法  help(tuple)
首先定义一个比较长的元组，使用count和index来查询元素
```python
In [84]: yl = (a,tl,x,t,)

In [85]: yl
Out[85]: (123, ('x', 54), 'qerasd', ('y', 1, ('qerasd', 1)))
help (tuple)可以获取tuple的使用方法，这里列出count和index方法
```
###count方法
指定查询元素，有命中返回1，没有则返回0
```python
In [90]: yl.count(1)
Out[90]: 0

In [91]: yl.count(a)
Out[91]: 1

In [92]: yl.count(t)
Out[92]: 1
```
count方法里指定元素带单引号的表示去tuple元素中的值，不带单引号表示取tuple中的变量
```python
In [99]: yl.count('sa')
Out[99]: 0

In [100]: yl.count('qerasd')
Out[100]: 1
```
不带单引号表示取tuple中的变量，变量不存在则会返回异常
```python
In [101]: yl.count(tl)
Out[101]: 1
变量不存在则会返回异常
In [102]: yl.count(d)
---------------------------------------------------------------------------
NameError                     Traceback (most recent call last)
<ipython-input-96-9b19996413ed> in <module>()
----> 1 yl.count(d)

NameError: name 'd' is not defined
```
###tuple中的index方法
index是查询元素索引位，如yl的tuple序列是yl = (a,tl,x,t,)    查询变量a、t和tl元素所在的位置分别是0、3和1位
```python
In [103]: yl.index(a)
Out[103]: 0

In [104]: yl.index(t)
Out[104]: 3

In [105]: yl.index(tl)
Out[105]: 1
```
##python列表(list)
列表是处理一组有序项目的数据结构，即可以在列表中存储一个序列的项目
列表是可变的数据结构，处理数据更加灵活
列表以中括号定义
列表定义
以下操作包含元组，列表的混合，请细致理解
```python
In [106]: list1 = ['a',1,(yl,),['hello world','python']]

In [107]: list1
Out[107]: 
['a',
 1,
 ((123, ('x', 54), 'qerasd', ('y', 1, ('qerasd', 1))),),
 ['hello world', 'python']]

In [108]: len (list1)
Out[108]: 4
list1中包含字符a、数值1、元组yl的元素和内置列表内的heello world，python的元素内容
```
###向列表中追加元素
创建一个list2的空列表，然后向列表中追加一个元素，再将list1和list2相加输出显示
```python
In [12]: list2
Out[12]: []
In [13]: list2.append('name')
In [14]: list1 + list2
Out[14]: 
['a',
 1,
 (((123, ('x', 54)), 'qerasd', ('y', 1, 'qerasd,1')),),
 ['hello world', 'python'],
 'name']
In [15]: help(list.remove)
Help on built-in function remove:
remove(...)
    L.remove(value) -- remove first occurrence of value.
    Raises ValueError if the value is not present.
```
###列表重复输出
将多个列表相加，使用*号运算符指定重复的次数，如(list1 + list2) * 2，会输出一个大的列表，列表元素是多个列表重复的次数
```python
In [17]: (list1 + list2) * 3
Out[17]: 
['a',
 1,
 (((123, ('x', 54)), 'qerasd', ('y', 1, 'qerasd,1')),),
 ['hello world', 'python'],
 'name',
 'a',
 1,
 (((123, ('x', 54)), 'qerasd', ('y', 1, 'qerasd,1')),),
 ['hello world', 'python'],
 'name',
 'a',
 1,
 (((123, ('x', 54)), 'qerasd', ('y', 1, 'qerasd,1')),),
 ['hello world', 'python'],
 'name']
```
###删除列表和删除列表元素
根据列表位置删除元素使用del list[元素位置]  来删除
```python
In [20]: list3
Out[20]: 
['a',
 1,
 (((123, ('x', 54)), 'qerasd', ('y', 1, 'qerasd,1')),),
 ['hello world', 'python'],
 'name']
In [21]: del list3[2]
In [22]: list3
Out[22]: ['a', 1, ['hello world', 'python'], 'name']
```
###list.remove(元素或元素位置) 
直接在这个列表中删除该元素，这里指定的是元素1，因为元素和元素位一样的关系，这里显示的效果并不突出
删除list3列表里的元素
```python
In [22]: list3
Out[22]: ['a', 1, ['hello world', 'python'], 'name']
In [23]: list3.remove(1)
In [24]: list3
Out[24]: ['a', ['hello world', 'python'], 'name']
```
###查询列表并删除元素使用list.pop(元素位置) 
取出的元素显示后会从该列表中删除，严格来说这种方法是取值，因为它会输出取值到元素，这种方法经常用于定数循环，比如for的数值循环
```python
In [24]: list3
Out[24]: ['a', ['hello world', 'python'], 'name']
In [25]: list3.pop(2)
Out[25]: 'name'
In [26]: list3
Out[26]: ['a', ['hello world', 'python']]
```
###在列表中插入元素
这里在列表的顺数二位(从0开始)，插入一个yl元组，结果如下
同样，insert方法可以插入一个空列表或其他空
```python
In [35]: list3.insert(2,yl)
In [36]: list3
Out[36]: 
['a',
 ['hello world', 'python'],
 ((123, ('x', 54)), 'qerasd', ('y', 1, 'qerasd,1'))]
 ```
###定义一个空元组，然后使用列表的insert方法将元组插入到从零开始的第二位
```python
n [38]: tuyl
Out[38]: ()
In [39]: 
In [39]: list3.insert(2,tuyl)
In [40]: list3
Out[40]: 
['a',
 ['hello world', 'python'],
 (),
 ((123, ('x', 54)), 'qerasd', ('y', 1, 'qerasd,1'))]
```
###将列表按照数值、列表、字符串和元组的规则来排序
```python
In [52]: list2
Out[52]: [1, 2, 3, 'a', 'b', 'c', (1,), (2,), (3,), [1], [2], [3]]
In [53]: list2.sort()
In [54]: list2
Out[54]: [1, 2, 3, [1], [2], [3], 'a', 'b', 'c', (1,), (2,), (3,)]
```
###在列表中取出元素和列表元素的循环迭代(循环)
字符串、元组、数字、列表、有序集合都是可迭代的对象，凡是可迭代的对象都可以使用for循环来访问
```python
list3.pop 取出序列元素(不是读取的含义，而是把数据从内存中拿取出来，显示后会"消失")
In [24]: list3
Out[24]: ['a', ['hello world', 'python'], 'name']
In [25]: list3.pop(2)
Out[25]: 'name'
In [26]: list3
Out[26]: ['a', ['hello world', 'python']]
```
###列表元素的extend循环方法(使用range来赋值)
```python
In [57]: list4.extend(range(10))
In [58]: list4
Out[58]: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9] 将10的迭代追加到list4列表当中
```
###在列表里加入空列表
在列表的1和5位置添加一个空的列表
```python
In [74]: list3.insert(1,[])
In [75]: list3.insert(5,[])
In [76]: list3
Out[76]: 
[['hello world', 'python'],
 [],
 'a',
 (),
 ((123, ('x', 54)), 'qerasd', ('y', 1, 'qerasd,1')),
 []]
 ```
###在空列表1中添加一个数值元素，添加时指定元素位(列表位置)
```python
In [91]: list3[1].append(114514)
In [92]: list3
Out[92]: 
[['hello world', 'python', 114514],
 [114514],
 'a',
 (),
 ((123, ('x', 54)), 'qerasd', ('y', 1, 'qerasd,1')),
 []]
 ```
###在指定的下标添加数值,如在列表中插入新的元素，在元素第六位添加一个hello world字符串
```python
In [111]: list3.insert(6,['hello world'])
In [112]: list3
Out[112]: 
[['hello world', 'python', 114514],
 [114514],
 'a',
 (),
 ((123, ('x', 54)), 'qerasd', ('y', 1, 'qerasd,1')),
 [],
 ['hello world']]
```
###列表查询例子
比如我需要创建一个句子，使用list.pop查询应用列表中的某一个元素，我可以将该列表元素直接应用到句子中，如：
取出的元素则会在显示后被删除
```python
In [45]: motorcycles = ['honda','yamaha','suzuki']
In [46]: print('The first motorcycle I owned was a ' + motorcycles.pop(0) + '.') 
The first motorcycle I owned was a honda.
In [47]: print (motorcycles)
['yamaha', 'suzuki']
```