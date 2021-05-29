# 19/4.2021 python复习

### **while循环**

```python
condition = 1
while condition < 10: #pyton中重要的是“：”加上之后下行会自动空四行
    print(condition)  #在python中是靠缩进来代替C中的“{}”，所以在代码过程中需要注意这种要求
    condition = condition+1 
    

```

![image-20210419211328831](C:\Users\jeff\AppData\Roaming\Typora\typora-user-images\image-20210419211328831.png)



当一直进行while循环的时候，I‘m True会一直无限循环下去，使用CTRL+C可以终止例程

```python
while True:
    print("I' Ture")
    
```

![image-20210419212113861](C:\Users\jeff\AppData\Roaming\Typora\typora-user-images\image-20210419212113861.png)



### **for 循环的复习**

```python
example_list = [1,2,3,4,5,6,7,132,5745,176234,2,7]

for i in example_list:
    print(i)
# for i in range(1,10,3):

    # print('inner of for')
print('outer of for')

D:\python3.7\python.exe D:/PyCharm/shi.py
1
inner of for
2
inner of for
3
inner of for
4
inner of for
5
inner of for
6
inner of for
7
inner of for
132
inner of for
5745
inner of for
176234
inner of for
2
inner of for
7
inner of for
outer of for


example_list = [1,2,3,4,5,6,7,132,5745,176234,2,7]

for i in example_list:
    print(i)
# for i in range(1,10,3):

    print('inner of for')
print('outer of for')

D:\python3.7\python.exe D:/PyCharm/shi.py
1
2
3
4
5
6
7
132
5745
176234
2
7
outer of for


for i in range(1,10,3):
    print(i)
D:\python3.7\python.exe D:/PyCharm/shi.py
1
4
7
    
    
```

#1 range（1，10，3）1和3指print的值从1开始小于10的整数，3表示从1开始每次叠加3位数输出结果，如上输出结果。

# 20/4.2021python复习

### **if/if elif/ 条件语句**

```python
x=-3
y=2
z=3
 if x>1:
     print('x is greater than y')
elif x<-1:
     print('x<-1')
elif x<1:
    print('x<1')
else:
     pirnt('x=1')

```

当x符合其中的条件，就会跳到最后结果![image-20210425221921185](C:\Users\jeff\AppData\Roaming\Typora\typora-user-images\image-20210425221921185.png)

# 22/4 2021python复习

### def 函数

```python
def function():
    print('This is a function')
    a=1+9
    print(a)

function()
```

![image-20210425222011024](C:\Users\jeff\AppData\Roaming\Typora\typora-user-images\image-20210425222011024.png)

### 函数 参数

```python
 def function():
     print('This is a function')
     a=1+9
     print(a)
function()

def fun(a,b):
    c = a*b
    print('the c is',c)
fun(3,2)
fun(a=3,b=9)
```

![image-20210425220812131](C:\Users\jeff\AppData\Roaming\Typora\typora-user-images\image-20210425220812131.png)

![image-20210425220716247](C:\Users\jeff\AppData\Roaming\Typora\typora-user-images\image-20210425220716247.png)

### def 默认函数参数

```python
def sale_car(price,brand,colour,is_second_hand):
    print('price:',price,
          'colour:',colour,
          'brand:',brand,
          'is_second_hand:',is_second_hand,)
sale_car(1233,'red','carmy',True)
```

![image-20210425222047404](C:\Users\jeff\AppData\Roaming\Typora\typora-user-images\image-20210425222047404.png)

### global or local

```python
APPLE = 100
def fun():
    a = 20
    return a+100
print(APPLE)
print(a)
```

![image-20210426150602976](C:\Users\jeff\AppData\Roaming\Typora\typora-user-images\image-20210426150602976.png)

当定义了global之后，a属于局部变量无法输出，需要和APPLE一样在开头进行global

```python
APPLE = 100
a = None
def fun():
    global a
    a = 20
    return a+100
print(APPLE)
print('a past=',a)
print(fun())
print('a now=',a)
```

![image-20210426151230662](C:\Users\jeff\AppData\Roaming\Typora\typora-user-images\image-20210426151230662.png)

需要先输出fun（）然后再输出a的值，否者会出现a=None，无法运行return的情况

# 27/4 2021Python复习

### Class类

```python
class Calculator:
    name = 'Good calculator'
    price = 18
    def add(self,x,y):
        print(self.name)
        result = x+y
        print(result)
    def minus(self,x,y):
        result = x-y
        print(result)
    def times(self,x,y):
        print(x*y)
    def divide(self,x,y):
        print(x/y)
Calcul = Calculator()
Calcul.divide(13,9)
```

![image-20210503105042783](C:\Users\jeff\AppData\Roaming\Typora\typora-user-images\image-20210503105042783.png)

使用类可以设计一个简单的计算机Calculator。

### 类int功能

```python
class Calculator:
    name = 'Good calculator'
    price = 18
    def __init__(self,name,price,hight=18,width=29,weight=15):
        self.name = name
        self.price = price
        self.h = hight
        self.wi = width
        self.we = weight
    def add(self,x,y):
        print(self.name)
        result = x+y
        print(result)
    def minus(self,x,y):
        result = x-y
        print(result)
    def times(self,x,y):
      print(x*y)
    def divide(self,x,y):
      print(x/y)
c= Calculator('Bad calculator',12)
c.h

```

- > #。。。。。。。。但是这个在pycharm中一直无法显示结果，暂时留一个疑问。。。。。。。。。。#

******2021/5/1问题已解决，如下图所示，问题在于pycharm中无法读取这种操作，使用python shell则完全可以运行，并且可以完全实现视频中的操作。但是初学水平有限，不清楚为什么pycharm不认可此种操作，或者是需要其他的步骤才能成功运行代码。。。。。。。。。。。**

![image-20210508223302681](C:\Users\jeff\AppData\Roaming\Typora\typora-user-images\image-20210508223302681.png)

### input 输入

```python
a_input = int(input('Please give a number:'))
if a_input == 1:
    print('This is a good one')
elif a_input == 2:
    print('See you next time')
else:
    print('Good luck')
```

![image-20210507215322699](C:\Users\jeff\AppData\Roaming\Typora\typora-user-images\image-20210507215322699.png)

input就是会在输出的屏幕中输入数字，然后把数字赋值给他，

### 元组 列表

元组为tuple，一般为一串数据

列表为list，有中括号的数据

可以进行迭代和定位

```python
>>> a_tuple = (12,3,45,83,3)
>>> another_tuple= 2,3,5,7,3,45
>>> 
>>> a_list=[12,4,57,43,434]
>>> 
>>> for index in range(len(a_list)):
	print('index=',index,'number in list',a_list[index])
	a_list[2]

index= 0 number in list 12
57
index= 1 number in list 4
57
index= 2 number in list 57
57
index= 3 number in list 43
57
index= 4 number in list 434
57
>>> for index in range(len(a_tuple)):
	print('index=',index,'number in tuple',a_tuple[index])

	
index= 0 number in tuple 12
index= 1 number in tuple 3
index= 2 number in tuple 45
index= 3 number in tuple 83
index= 4 number in tuple 3
>>> for index in range(len(another_tuple)):
	print('index=',index,'number in tuple',another_tuple[index])

	
index= 0 number in tuple 2
index= 1 number in tuple 3
index= 2 number in tuple 5
index= 3 number in tuple 7
index= 4 number in tuple 3
index= 5 number in tuple 45
>>> 

```

通过tuple和list的不同程序输出不难看出，tuple和list的运行规律基本相同。

### 列表

列表就是一系列有序的数列，**<!--数列的顺序是从0开始的-->**

```python
 a = [1,2,3,4,2,3,4,5,43]
>>> 

>>> a.append(0) #append(x)在列表的最后面添加x
>>> print(a)
[1, 2, 3, 4, 2, 3, 4, 5, 43, 0]

>>> a.insert(1,0)  #insert(x,y)在列表中的第x个数加入y
>>> print(a)
[1, 0, 2, 3, 4, 2, 3, 4, 5, 43, 0]

>>> a.remove(2)  #a.remove(x)删除列表中出现的第一个x
>>> print(a)
[1, 0, 3, 4, 2, 3, 4, 5, 43, 0]

>>> print(a[2])  #print（a【x】）索引列表中第x个数的值
3
>>> print(a[-1])  #加入负号从后面倒过来算
0

>>> print(a[0:4])  #print（a【x:y】）加入冒号表示显示从x位到y位的列表
[1, 0, 3, 4]
>>> print(a[:4])  #print（a【：y】）从第零位开始到y位可以不显示，同样输出。同理可得从后面开始算起y也可以省略，灵活使用
[1, 0, 3, 4]

>>> print(a.index(4))#a.index(x)从第0个开始算出现x的数是排在第几个
3
>>> print(a.count(4))#a.count（x）在整个列表中x出现的次数
2

>>> a.sort()#使列表从小到大进行排列
>>> print(a)
[1, 2, 2, 3, 3, 4, 4, 5, 43]
>>> a.sort(reverse=True)#使列表从大到小进行排列
>>> print(a)
[43, 5, 4, 4, 3, 3, 2, 2, 1]
```

### 多维列表

**建议添加numpy or pandas进行多维、矩阵的运算**

```python
>>> multi_dim_a = [[1,2,3],[2,3,4],[3,4,5]] #把显示的数组看成一个3✖3的矩阵
>>> print(multi_dim_a[2][2]) #输出第2行第2列的矩阵值，*从0行0列开始计算
5
```

### 字典 dictionary

一个没有顺序的容器，以大括号的形式出现

```python
>>> d = {'apple':1,'pear':2,'orange':3}
>>> d2 = {1:'a','c':'b'}

>>> print(d['apple'])#在字典中查找apple，就会输出apple对应的1
1

>>> del d['pear'] #删除字典中的值
>>> print(d)
{'apple': 1, 'orange': 3}

>>> d['b']=20 #把该值加入字典中，但是字典使无序性的
>>> print(d)
{'apple': 1, 'orange': 3, 'b': 20}

>>> d = {'apple':[1,2,3],'pear':{1:3,3:'a'},'orange':3}
>>> print(d['pear'][3])
a  #可以在字典中加入字典或者列表，如程序中在pear中找3对应的是‘a’
```

### import 载入模块



```python
>>> import time #加载模块的方法，其一
>>> 
>>> print(time.localtime())
time.struct_time(tm_year=2021, tm_mon=4, tm_mday=27, tm_hour=21, tm_min=54, tm_sec=42, tm_wday=6, tm_yday=143, tm_isdst=0)
```

```python
>>> import time as t #或者可以把一大串的单词as成单个的字母代替，其二
>>> print(t.localtime())
time.struct_time(tm_year=2021, tm_mon=4, tm_mday=27, tm_hour=21, tm_min=59, tm_sec=37, tm_wday=6, tm_yday=143, tm_isdst=0)
```

```python
>>> from time import time,localtime #其三
>>> print(localtime())
time.struct_time(tm_year=2021, tm_mon=4, tm_mday=27, tm_hour=22, tm_min=4, tm_sec=1, tm_wday=6, tm_yday=143, tm_isdst=0)
>>> print(time())
1621778652.4412289
```

```python
>>> from time import* #其四
>>> print(localtime())
time.struct_time(tm_year=2021, tm_mon=4, tm_mday=27, tm_hour=22, tm_min=5, tm_sec=46, tm_wday=6, tm_yday=143, tm_isdst=0)
>>> print(time())
1621778756.4606805
```

```python
>>> a = [1,2,3]
>>> b = [4,5,6]
>>> zip(a,b)
<zip object at 0x000001A3FB3A04C8>
>>> list(zip(a,b))
[(1, 4), (2, 5), (3, 6)]
>>> for i,j in zip(a,b)
SyntaxError: invalid syntax
>>> for i,j in zip(a,b):
	print(i/2,j*2)

	
0.5 8
1.0 10
1.5 12
>>> 
```

### zip lambad map

```python
>>> a = [1,2,3]
>>> b=[4,5,6]
>>> zip(a,b)
<zip object at 0x000001DE714FC388>
>>> list(zip(a,b))
[(1, 4), (2, 5), (3, 6)]
>>> for i,j in zip(a,b):
	print(i/2,j*2)

	
0.5 8
1.0 10
1.5 12
>>> list(zip(a,b))
[(1, 4), (2, 5), (3, 6)]
```

```python
>>> def fun1(x,y):
	return(x+y)

>>> fun1(2,3)
5
```

```python
>>> fun2=lambda x,y:x+y
>>> fun2(2,3)
5
>>> map(fun1,[1],[2])
<map object at 0x000001DE714EECC0>
>>> list(map(fun1,[1],[2]))
[3]
>>> list(map(fun1,[1,3],[2,5]))
[3, 8]
>>> 

```

### 浅复制&深复制，copy & deep copy

```python
>>> import copy#copy是一个模块
>>> a = [1,2,3]
>>> b = a
>>> id(a)#id是一个独特的空间
3175055225672
>>> id(b)
3175055225672
>>> b[0] = 11
>>> a
[11, 2, 3]
>>> a[1] = 22
>>> b
[11, 22, 3]#无论改变a[]中的值还是b【】中的值都是一起改变的
>>> print(id(a) == id(b))
True
>>> c = copy.copy(a)#浅copy
>>> print(id(a)==id(c))
False
>>> c[1] = 22222
>>> a
[11, 22, 3]#
>>> c
[11, 22222, 3]
>>> a[1,2,[3,4]]
>> a=[1,2,[3,4]]
>>> d = copy.copy(a)
>>> id(a) = id(d)
SyntaxError: can't assign to function call
>>> id(a) == id(d)
False
>>> id(a[2][0]) = 333
SyntaxError: can't assign to function call
>>> id(a[2]) == id(d[2])
True
>>> a[0] = 11
>>> b
[11, 22, 3]
>>> d
[1, 2, [3, 4]]
>>> a[2][0] = 333
>>> d
[1, 2, [333, 4]]
>>> e = copy.deepcopy(a)#完全copy
>>> id(e[2]) == id(a[2])
False
>>> 
```



# 1/5 2021 python

### set 找不同

```python
>>> char_list = ['a','b','c','c','d','d','d']
>>> sentence = 'Welcome Back to This Tutorial'
>>> 
>>> print(set(sentence))
{'k', 'u', ' ', 'W', 'h', 'B', 's', 't', 'c', 'i', 'r', 'a', 'l', 'T', 'o', 'e', 'm'}
>>> unique_char=set(char_list)
>>> unique_char.add('a')
>>> print(unique_char.remove('a'))
None

>>> char_list = ['a','b','c','c','d','d','d']
>>> sentence = 'Welcome Back to This Tutorial'
>>> unique_char=set(char_list)
>>> unique_char.add('x')
>>> 
>>> set1 = unique_char
>>> set2 = {'a','e','i'}
>>> print(set1.difference(set2))#找不同的
{'x', 'c', 'd', 'b'}
>>> print(set1.intersection(st2))#找相同
{'a'}
>>> 
```



完结！！！