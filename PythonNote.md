# Python

在Linux环境下
## 一. 开发环境
### 编辑器、编译器选择
Linux下，shell中键入python，启动解释器。
Ctrl-d退出提示符。（windows下为Ctrl-z再按Enter）

在windows下建议使用IDLE；
在linux下可以使用vim或emacs；
sublime也行；

开发大型程序推荐使用IDE；

如何编写Python程序 下面是保存和运行Python程序的标准流程。  

    1. 打开你最喜欢的编辑器。
    2. 输入例子中的程序代码。
    3. 用注释中给出的文件名把它保存为一个文件。我按照惯例把所有的Python程序都以扩展名.
    py保存。
    4. 运行解释器命令python program.py或者使用IDLE运行程序。你也可以使用先前介绍的可执
    行的方法。

### 使用源文件
shell下编译运行源文件方式：$ python filename.py

一个简单的源文件
```python
#!/usr/bin/python
# Filename: helloworld.py
#hellowordl.py
print'Hello World'
```


*注意：python对大小写敏感*
注释标志为‘#’，相对于C/C++中对‘//’

*PS:你可以把你的程序保存在PATH环境变量中的目录之一。每当你运行任何程序，系统会查找列在PATH环境变量中的各个目录。然后运行哪个程序。你只要简单地把这个源文件复制到PATH所列目录之一就可以使你的程序在任何位置都可用*


### 获取帮助
运行help(str)会显示str类的帮助。
str？

## 二. 基本概念
### 字面意义的常量
python中有4种类型的数：整数、长整数、浮点数和复数。  
例：2、9、-1；长整数是大一些的整数；2.34、2.23E-4;(-5+4j)、(23-4.6j);

### 字符串
· 使用单引号(' ')：指示字符串；  
· 使用双引号(" ")：与单引号相同，实际上单引号和双引号完全相同；  
· 使用三引号(''' '''或"' '")：指示一个多行的字符串，可以在三引号中自由使用单引号和双引号；  
· 转义符：利用在特殊符号前加反斜杠 \ 来帮助输出，如 \' 输出单引号，\ \ 输出反斜杠本身；  
*注意：在字符串行末的单独一个反斜杠表示字符串在下一行继续，而不是开始新的一行*  
· 自然字符串：指示某些不需要如转义符那样的特殊处理的字符串，则需要指定一个自然字符串，通过在字符串前加上前缀r或R来指定，如 r"string"；  
· Unicode字符串： 书写国际文本的标准方法，在字符串前加上前缀u或U，如u"string"；  
· 字符串是不可变的： 创造后不可以再改变；  
· 按字面意义级连字符串： 两个字面意义相邻的字符串会被python自动级连，如'What\'s ''your name?'会自动转为"What's your name?"；  
**在python中没有char数据类型**  
**一定要用自然字符串处理正则表达式，不然会需要使用很多反斜杠** 

### 变量
使用变量时只需要给它们赋一个值，不需要声明或定义数据类型。  
直接定义或赋值
```python
counter = 100 # 赋值整型变量
miles = 1000.0 # 浮点型
name = "John" # 字符串
```

多变量赋值
```python
a = b = c = 1
a,b,c = 1, 2, "John"
```

### 标志符的命名
变量是标识符的例子。  
命名规则与C/C++相同。

### 数据类型
变量可以处理不同类型的值，称为数据类型。基本的类型是**数**和**字符串**。

### 对象
Python把在程序中用到的任何东西都称为 *对象*；

### 逻辑行与物理行
物理行是你在编写程序时所看见的；逻辑行是Python看见的单个语句。  
Python假定每个物理行对应一个逻辑行。  
如果想要在一个物理行中使用多于一个逻辑行，那么需要使用分号(;)来特别标明，分号表示一个逻辑行语句的结束；  
```python
i = 5
print i
#等价于
i = 5;
print i;
#等价于
i = 5;print i;
```

**强烈建议坚持每个物理行只写一句逻辑行，除非逻辑行太长了**  
**而且很少在python程序中使用或看到分号**

多个物理行中写一个逻辑行的例子
```python
print \
i
#等价于
print i
```

### 缩进
在逻辑行首的空白(空 格和制表符)用来决定逻辑行的缩进层次，从而用来决定语句的分组。这意味着同一层次的语句必须有相同的缩进。每一组这样的语句称为一个块。

**不要混合使用制表符和空格来缩进，要么在每个缩进层次只使用单个制表符表示或两个/四个空格（三种风格中选其一坚持，最好选第一种）**


## 三. 运算符与表达式
### 运算符
运算符：说明、名称（例子）  
+、-、*、/： 加减乘除（整数除法得到整数）；  
**： 幂，3\*\*4=81；  
//：取整除，返回商的整数部分，4//3.0=1.0；  
%：取模；  
<<、>>：左移、右移，二进制比特位移动；  
&、|、^、~：按位与、或、异或、翻转；  
<、>、<=、>=、==、!=：比较运算符；  
not、and、or：布尔非、与、或，相当于C/C++中的!、&&、||；  

**优先级参看优先级表，正确使用圆括号**

### 表达式
```python
#!/usr/bin/python
# Filename: expression.py
length = 5
breadth = 2
area = length * breadth
print 'Area is', area
print 'Perimeter is', 2 * (length + breadth) #自发的添加空格在is与后面的数字之间
```
输出为：
```shell
Area is 10  
Perimeter is 14
```
## 控制流
**if、for和while**

### if语句
if 条件判断 :  
    ...  
elif 条件判断 :  
    ...  
else :  
    ...  
```python
#!/usr/bin/python # Filename: if.py
number = 23
guess = int(raw_input('Enter an integer : '))
if guess == number:
    statement...
elif guess < number:
    statement...
else:
    statement...
```

**注意：在python中没有switch语句**

### while语句
只要在一个条件为真的情况下，while语句允许你重复执行一块语句。while语句是所谓 循环 语 句的一个例子。while语句有一个可选的else从句。
```python
#!/usr/bin/python
# Filename: while.py
number = 23 running = True
while running:
    guess = int(raw_input('Enter an integer : '))
    if guess == number:
        print 'Congratulations, you guessed it.'
        running = False # this causes the while loop to stop
    elif guess < number:
        print 'No, it is a little higher than that'
    else:
        print 'No, it is a little lower than that'
else:
    print 'The while loop is over.'
    # Do anything else you want to do here
print 'Done'

```

输出：  
```shell
Enter an integer : 50  
No, it is a little lower than that. Enter an integer : 22  
No, it is a little higher than that. Enter an integer : 23 Congratulations,   you guessed it. The while loop is over.  
Done  
```
*可以在while循环中使用一个else从句**

### for语句
for...in：在一序列的对象上递归，即逐一使用队列中的每个项目。

```python
#!/usr/bin/python 
# Filename: for.py
for i in range(1, 5): 
    print i
else:
    print 'The for loop is over'
```

输出：  
```
1  
2  
3  
4  
The for loop is over
```


```python
#C/C++中
for (int i=0;i<5;i++)
#等价于
#python中
for i in range(0,5)
```

### break和continue语句
**在while或for语句中可以使用**


## 四. 函数

### 函数定义
函数通过def关键字定义。def关键字后跟一个函数的 标识符 名称，然后跟一对圆括号。圆括号 之中可以包括一些变量名，该行以冒号结尾。接下来是一块语句，它们是函数体。

```python
#!/usr/bin/python
# Filename: function1.py
def sayHello():
    print 'Hello World!' # block belonging to the function
sayHello() # call the function
```

### 函数形参

```python
#!/usr/bin/python
# Filename: func_param.py
def printMax(a, b): 
    if a > b:
        print a, 'is maximum' 
    else:
        print b, 'is maximum'

printMax(3, 4) # directly give literal values
x= 5 
y= 7
printMax(x, y) # give variables as arguments
```


### 局部变量
当你在函数定义内声明变量的时候，它们与函数外具有相同名称的其他变量没有任何关系，即变量名称对于函数来说是局部的。这称为变量的作用域。所有变量的作用域是它们被定义的块，从它们的名称被定义的那点开始。

#### global语句
如果你想要为一个定义在函数外的变量赋值，那么你就得告诉Python这个变量名不是局部的，而是全局的。我们使用global语句完成这一功能。没有global语句，是不可能为定义在函数外的变量赋值的。
你可以使用定义在函数外的变量的值(假设在函数内没有同名的变量)。然而，并不鼓励你这样做，并且应该尽量避免这样做，因为这使得程序的读者会不清楚这个变量是在哪里定义的。使用global语句可以清楚地表明变量是在外面的块定义的。

```python
#!/usr/bin/python
# Filename: func_global.py
def func(): 
    global x

    print 'x is', x
    x = 2
    print 'Changed local x to', x

x = 50
func()
print 'Value of x is', x
```

输出：  
```shell
x is 50  
Changed global x to 2   
Value of x is 2  
```

**可以使用同一个global语句指定多个全局变量。例如global x, y, z**

### 默认参数值
可以在函数定义的形参名后加上赋值运算符(=)和默认值，从而给形参指定默认参数值。

```python
#!/usr/bin/python
# Filename: func_default.py
def say(message, times = 1): 
    print message * times 
say('Hello') 
say('World', 5)
```
输出： 
```shell 
Hello   
WorldWorldWorldWorldWorld  
```
**只有在形参表末尾的那些参数可以有默认参数值**


### 关键参数
如果你的某个函数有许多参数，而你只想指定其中的一部分，那么你可以通过命名来为这些参数赋值——这被称作‘关键参数’ ——我们使用名字(关键字)而不是位置(我们前面所一直使用的方法)来给函数指定实参。

这样做的优势：  
    1. 不必担心参数的顺序，使用函数变得更加简单了；  
    2. 假设其他参数都有默认值，我们可以只给我们想要的那些参数赋值。  

```python
#!/usr/bin/python
# Filename: func_key.py
def func(a, b=5, c=10):
    print 'a is', a, 'and b is', b, 'and c is', c

func(3, 7) 
func(25, c=24) 
func(c=50, a=100)
```
输出： 
```shell 
a is 3 and b is 7 and c is 10  
a is 25 and b is 5 and c is 24   
a is 100 and b is 5 and c is 50  
```

### return语句
return语句用来从一个函数返回即跳出函数。我们也可选从函数返回一个值。
```python
#!/usr/bin/python
# Filename: func_return.py
def maximum(x, y): 
    if x > y:
        return x 
    else:
        return y
print maximum(2, 3)
```

**如果一个变量的值为None，可以表示它没有值**  
**除非你提供你自己的return语句，每个函数都在结尾暗含有return None语句**

### DocStrings
Python有一个很奇妙的特性，称为文档字符串，它通常被简称为docstrings。DocStrings是一个重要的工具，由于它帮助你的程序文档更加简单易懂，你应该尽量使用它。你甚至可以在程序运行的时候，从函数恢复文档字符串!


```python
#!/usr/bin/python
# Filename: func_doc.py
def printMax(x, y):
    '''Prints the maximum of two numbers.
    
    The two values must be integers.'''
    x = int(x) # convert to integers, if possible 
    y = int(y)

    if x > y:
        print x, 'is maximum'
    else:
        print y, 'is maximum'

printMax(3, 5)
print printMax.__doc__

```
输出：  
5 is maximum  
Prints the maximum of two numbers.  
    
   The two values must be integers.


**Prints前有一个制表符单位**

**解析**：  
在函数的第一个逻辑行的字符串是这个函数的‘文档字符串’；  
**惯例**：  
文档字符串的惯例是一个多行字符串，它的首行以大写字母开始，句号结尾。第二行是空行，从第三行开始是详细的描述。强烈建议在函数中使用文档字符串时遵循这个惯例。

可以使用__doc__(注意双下划线)调用printMax函数的文档字符串属性(属于函数的名称)。请记住Python把‘每一样东西’都作为‘对象’，包括这个函数。

如果你已经在Python中使用过help()，那么你已经看到过DocStings的使用了!它所做的只是抓 取函数的__doc__属性，然后整洁地展示给你。你可以对上面这个函数尝试一下——只是在你 的程序中包括help(printMax)。记住按q退出help。

**自动化工具也可以以同样的方式从你的程序中提取文档。因此强烈建议对所写的任何正式函数编写文档字符串**


## 五. 模块
模块基本上就是一个包含了所有你定义的函数和变量的文件。为了在其他程序中重用模块，模块的文件名必须以.py为扩展名。

### 使用sys模块

```python
#!/usr/bin/python
# Filename: using_sys.py
import sys  
    print 'The command line arguments are:' 
    for i in sys.argv:
        print i
    print '\n\nThe PYTHONPATH is', sys.path, '\n'
```

输出：  
The command line arguments are: using_sys.py  
we  
are arguments  
<br><br>
The PYTHONPATH is ['/home/swaroop/byte/code', '/usr/lib/python23.zip', '/usr/lib/python2.3', '/usr/lib/python2.3/plat-linux2', '/usr/lib/python2.3/lib-tk', '/usr/lib/python2.3/lib-dynload', '/usr/lib/python2.3/site-packages', '/usr/lib/python2.3/site-packages/gtk-2.0']

**sys是system的缩写**  
sys模块中的argv变量通过使用点号指明——sys.argv——这种方法的一个优势是这个名称不会与任何在你的程序中使用的argv变量冲突。另外，它也清晰地表明了这个名称是sys模块的一部分。  
sys.argv变量是一个字符串的列表。特别地，sys.argv包含了命令行参数的列表，即使用命令行传递给你的程序的参数。

**python也是从0开始计数的**


### 字节编译的.pyc文件
输入一个模块相对来说是一个比较费时的事情，所以Python做了一些技巧，以便使输入模块更加快一些。一种方法是创建字节编译的文件，这些文件以.pyc作为扩展名。字节编译的文件与Python变换程序的中间状态有关。当下次从别的程序输入这个模块的时候，.pyc文件是十分有用的——它会快得多，因为一部分输入模块所需的处理已经完成了。另外，这些字节编译的文件也是与平台无关的。

### from..import语句
如果你想要直接输入argv变量到你的程序中(避免在每次使用它时打sys.)，那么你可以使用from sys import argv语句。如果你想要输入所有sys模块使用的名字，那么你可以使用from sys import *语句。这对于所有模块都适用。一般说来，应该避免使用from..import而使用import语句，因为这样可以使你的程序更加易读，也可以避免名称的冲突。

### 模块的\_\_name\_\_
**双下划线**

每个Python模块都有它的\_\_name\_\_，如果它是'\_\_main\_\_'，这说明这个模块被用户单独运行， 我们可以进行相应的恰当操作。

```python
#!/usr/bin/python
# Filename: using_name.py
if __name__ == '__main__':
    print 'This program is being run by itself'
else:
    print 'I am being imported from another module'
```
输出：  
$ python using_name.py  
This program is being run by itself

$ python  
\>\>\> import using_name  
I am being imported from another module  
\>\>\>


### 制作自己的模块

以下是一个模块的例子：
```python
#!/usr/bin/python
# Filename: mymodule.py
def sayhi():
    print 'Hi, this is mymodule speaking.'
version = '0.1'
# End of mymodule.py
```

将上面这个模块保存放在以下程序的统一目录下：
```python
#!/usr/bin/python
# Filename: mymodule_demo.py
import mymodule

mymodule.sayhi()
print 'Version', mymodule.version
```
输出：  
```shell
$ python mymodule_demo.py  
Hi, this is mymodule speaking.  
Version 0.1
```

#### from..import
下面是一个使用from..import语法的版本  
```python
#!/usr/bin/python
# Filename: mymodule_demo2.py

from mymodule import sayhi, version 
# Alternative:
# from mymodule import *

sayhi()
print 'Version', version
```


### dir()函数
可以使用内建的dir函数来列出模块定义的标识符。标识符有函数、类和变量。  

当你为dir()提供一个模块名的时候，它返回模块定义的名称列表。如果不提供参数，它返回当前模块中定义的名称列表。  

**模块的用处在于它能为你在别的程序中重用它提供的服务和功能。Python附带的标准库就是这 样一组模块的例子**



## 六. 数据结构

在python中有三种内建的数据结构--**列表、元组和字典**。


### 列表
list是处理一组有序项目的数据结构，即你可以在一个列表中存储一个序列的项目。在Python中，每个项目之间用 **逗号**分割。

列表中的项目应该包括在方括号中，这样Python就知道你是在指明一个列表。一旦你创建了一个列表，你可以 **添加、删除或是搜索**列表中的项目。由于你可以增加或删除项目，我们说列表是 **可变**的数据类型，即这种类型是可以被改变的。


```python
#!/usr/bin/python
# Filename: using_list.py

# This is my shopping list
shoplist = ['apple', 'mango', 'carrot', 'banana']

print 'I have', len(shoplist),'items to purchase.'

print 'These items are:', # Notice the comma at end of the line for item in shoplist:
    print item,

print '\nI also have to buy rice.' shoplist.append('rice')
print 'My shopping list is now', shoplist

print 'I will sort my list now' 
shoplist.sort()
print 'Sorted shopping list is', shoplist

print 'The first item I will buy is', shoplist[0] 
olditem = shoplist[0]
del shoplist[0]
print 'I bought the', olditem
print 'My shopping list is now', shoplist

```

输出：  
```shell
$ python using_list.py
I have 4 items to purchase.
These items are: apple mango carrot banana
I also have to buy rice.
My shopping list is now ['apple', 'mango', 'carrot', 'banana', 'rice'] 
I will sort my list now
Sorted shopping list is ['apple', 'banana', 'carrot', 'mango', 'rice'] The first item I will buy is apple
I bought the apple
My shopping list is now ['banana', 'carrot', 'mango', 'rice']
```

append方法：添加一个项目；  
sort方法：对列表排序；  
del listname[i]：删除某一项目；  


### 元组
元组和列表十分类似，只不过元组和字符串一样是 **不可变**的 即你不能修改元组。元组通过 **圆括号中用逗号分割**的项目定义。元组通常用在使语句或用户定义的函数能够安全地采用一组值的时候，即被使用的元组的值不会改变。 

```python
#!/usr/bin/python
# Filename: using_tuple.py

zoo = ('wolf', 'elephant', 'penguin')
print 'Number of animals in the zoo is', len(zoo)

new_zoo = ('monkey', 'dolphin', zoo)
print 'Number of animals in the new zoo is', len(new_zoo) 
print 'All animals in new zoo are', new_zoo
print 'Animals brought from old zoo are', new_zoo[2] 
print 'Last animal brought from old zoo is', new_zoo[2][2]
```

Output: 
```shell
$ python using_tuple.py
Number of animals in the zoo is 3
Number of animals in the new zoo is 3  
All animals in new zoo are ('monkey', 'dolphin', ('wolf', 'elephant', 'penguin')) 
Animals brought from old zoo are ('wolf', 'elephant', 'penguin')
Last animal brought from old zoo is penguin
```

**可以通过len函数获取元组长度，说明元组也是一个序列**

含有0个或1个项目的元组。一个空的元组由一对空的圆括号组成，如myempty = ()。然而，含有单个元素的元组就不那么简单了。你必须在第一个(唯一一个)项目后跟一个逗号，这样Python才能区分元组和表达式中一个带圆括号的对象。即如果你想要的是一个包含项目2的元组的时候，你应该指明singleton = (2,)。

列表之中的列表不会失去它的身份，即列表不会像Perl中那样被打散。同样元组中的元组，或列表中的元组，或元组中的列表等等都是如此。只要是Python，它们就只是使用另一个对象存储的对象。

#### 元组与打印语句
元组最通常的用法是用在打印语句中


```python
#!/usr/bin/python
# Filename: print_tuple.py

age = 22
name = 'Swaroop'

print '%s is %d years old' % (name, age)
print 'Why is %s playing with that python?' % name
```


Output：
```shell
$ python print_tuple.py
Swaroop is 22 years old
Why is Swaroop playing with that python?
```

print语句可以使用跟着%符号的项目元组的字符串。这些字符串具备定制的功能。定制让输出满足某种特定的格式。定制可以是%s表示字符串或%d表示整数。元组必须按照相同的顺序来 对应这些定制。


### 字典
字典类似于你通过联系人名字查找地址和联系人详细情况的地址簿，即，我们把键(名字)和
值(详细情况)联系在一起。注意， **键必须是唯一的**，就像如果有两个人恰巧同名的话，你无
法找到正确的信息。

只能使用 **不可变的对象(比如字符串)来作为字典的键**，但是你可以把不可变或可变
的对象作为字典的值。基本说来就是，你应该只使用简单的对象作为键。

键值对在字典中以这样的方式标记:d = {key1 : value1, key2 : value2 }。注意它们的键/值对用冒号分割，而各个对用逗号分割，所有这些都包括在花括号中。

记住字典中的键/值对是没有顺序的。如果你想要一个特定的顺序，那么你应该在使用前自己对它们排序。

**字典是dict类的实例/对象**



```python
#!/usr/bin/python
# Filename: using_dict.py

# 'ab' is short for 'a'ddress'b'ook
ab = { 'Swaroop' : 'swaroopch@byteofpython.info', 
        'Larry' : 'larry@wall.org',
        'Matsumoto' : 'matz@ruby-lang.org',
        'Spammer' : 'spammer@hotmail.com' 
    }

print "Swaroop's address is %s" % ab['Swaroop']

# Adding a key/value pair 
ab['Guido'] = 'guido@python.org'

# Deleting a key/value pair 
del ab['Spammer']

print '\nThere are %d contacts in the address-book\n' % len(ab) 
for name, address in ab.items():
    print 'Contact %s at %s' % (name, address)

if 'Guido' in ab: # OR ab.has_key('Guido') 
    print "\nGuido's address is %s" % ab['Guido']
```

Output:
```shell
$ python using_dict.py
Swaroop's address is swaroopch@byteofpython.info

There are 4 contacts in the address-book

Contact Swaroop at swaroopch@byteofpython.info 
Contact Matsumoto at matz@ruby-lang.org 
Contact Larry at larry@wall.org
Contact Guido at guido@python.org

Guido's address is guido@python.org
```

### 序列
列表、元组和字符串都是序列，序列的两个主要特点是 **索引操作符和切片操作符**。索引操作符让我们可以从序列中抓取一个特定项目。切片操作符让我们能够获取序列的一个切片，即一部分序列。

```python
#!/usr/bin/python # Filename: seq.py
shoplist = ['apple', 'mango', 'carrot', 'banana']

# Indexing or 'Subscription' operation print 'Item 0 is', shoplist[0]
print 'Item 1 is', shoplist[1]
print 'Item 2 is', shoplist[2]
print 'Item 3 is', shoplist[3] 
print 'Item -1 is', shoplist[-1] 
print 'Item -2 is', shoplist[-2]

# Slicing on a list
print 'Item 1 to 3 is', shoplist[1:3] 
print 'Item 2 to end is', shoplist[2:] 
print 'Item 1 to -1 is', shoplist[1:-1] 
print 'Item start to end is', shoplist[:]

# Slicing on a string
name = 'swaroop'
print 'characters 1 to 3 is', name[1:3] 
print 'characters 2 to end is', name[2:] 
print 'characters 1 to -1 is', name[1:-1] 
print 'characters start to end is', name[:]
```


Output:
```shell
$ python seq.py
Item 0 is apple
Item 1 is mango
Item 2 is carrot
Item 3 is banana
Item -1 is banana
Item -2 is carrot
Item 1 to 3 is ['mango', 'carrot']
Item 2 to end is ['carrot', 'banana']
Item 1 to -1 is ['mango', 'carrot']
Item start to end is ['apple', 'mango', 'carrot', 'banana'] 
characters 1 to 3 is wa
characters 2 to end is aroop 
characters 1 to -1 is waroo 
characters start to end is swaroop
```

索引：  
索引来取得序列中的单个项目。这也被称作是下标操作。每当你用方括号中的一个数来指定一个序列的时候，Python会为你抓取序列中对应位置的项目。**索引同样可以是负数**，在那样的情况下，位置是从序列尾开始计算的。因此，shoplist[-1]表示 序列的最后一个元素而shoplist[-2]抓取序列的倒数第二个项目。

切片：  
切片操作符是序列名后跟一个方括号，方括号中有一对可选的数字，并用冒号分割。注意这与你使用的索引操作符十分相似。记住 **数是可选的，而冒号是必须的**。
切片操作符中的第一个数(冒号之前)表示切片开始的位置，第二个数(冒号之后)表示切片到哪里结束。如果不指定第一个数，Python就从序列首开始。如果没有指定第二个数，则Python会停止在序列尾。注意，返回的序列从开始位置开始，刚好在结束位置之前结束。即开始位置是包含在序列切片中的，而结束位置被排斥在切片外。  
可以用负数做切片。负数用在从序列尾开始计算的位置。例如，shoplist[:-1]会返回除了最后一个项目外包含所有项目的序列切片。


### 引用
当你创建一个对象并给它赋一个变量的时候，这个变量仅仅引用那个对象，而不是表示这个对象本身！也就是说，变量名指向你计算机中存储那个对象的内存。这被称作名称到对象的绑定。


```python
#!/usr/bin/python
# Filename: reference.py

print 'Simple Assignment'
shoplist = ['apple', 'mango', 'carrot', 'banana']
mylist = shoplist # mylist is just another name pointing to the same object!

del shoplist[0]
print 'shoplist is', shoplist
print 'mylist is', mylist
# notice that both shoplist and mylist both print the same list without 
# the 'apple' confirming that they point to the same object

print 'Copy by making a full slice'
mylist = shoplist[:] # make a copy by doing a full slice 
del mylist[0] # remove first item

print 'shoplist is', shoplist
print 'mylist is', mylist
# notice that now the two lists are different
```

Output:
```shell
$ python reference.py
Simple Assignment
shoplist is ['mango', 'carrot', 'banana'] 
mylist is ['mango', 'carrot', 'banana'] 
Copy by making a full slice
shoplist is ['mango', 'carrot', 'banana'] 
mylist is ['carrot', 'banana']
```

**记住列表的赋值语句不创建拷贝。你得使用切片操作符来建立序列的拷贝**


### 更多字符串的内容
字符串也是对象，在程序中使用的字符串都是str类的对象。

```python
#!/usr/bin/python
# Filename: str_methods.py

name = 'Swaroop' # This is a string object

if name.startswith('Swa'):
    print 'Yes, the string starts with "Swa"'

if 'a' in name:
    print 'Yes, it contains the string "a"'

if name.find('war') != -1:
    print 'Yes, it contains the string "war"'

delimiter = '_*_'
mylist = ['Brazil', 'Russia', 'India', 'China'] 
print delimiter.join(mylist)
```

Output:
```shell
$ python str_methods.py
Yes, the string starts with "Swa" 
Yes, it contains the string "a"
Yes, it contains the string "war" 
Brazil_*_Russia_*_India_*_China
```

**startwith** 方法是用来测试字符串是否以给定字符串开始。  
**in** 操作符用来检验一个给定字符串是否为另一个字符串的一部分。  
**find** 方法用来找出给定字符串在另一个字符串中的位置，或者返回-1以表示找不到子字符串。  
str类也有以一个作为分隔符的字符串 **join** 序列的项目的整洁的方法，它返回一个生成的大字符串。  






    Python学习笔记上篇结束，上篇主要内容是Python的基础知识。此部分内容可供大家参考查阅，笔记
    中大部分内容来源是参看Swaroop,C.H的书《简明Python教程》，有兴趣的朋友可以参看这边书。



***~~开源精神~~***





