# installing python
https://www.anaconda.com/download/

# 小练习
> Basic Practice:
http://codingbat.com/python
More Mathematical (and Harder) Practice:
https://projecteuler.net/archives
List of Practice Problems:
http://www.codeabbey.com/index/task_list
A SubReddit Devoted to Daily Practice Problems:
https://www.reddit.com/r/dailyprogrammer
A very tricky website with very few hints and touch problems (Not for beginners but still interesting)
http://www.pythonchallenge.com/

# 打开 anaconda jupyter
 - 新建 python3
 - .ipynb 表示 i python note book

# shift enter
 - 打开下一行

# get the course notebooks
 - https://github.com/Pierian-Data/Complete-Python-3-Bootcamp

 # mac进入 /users 目录
 - shift + command + G 输入路径

 # mac显示隐藏文件夹
 - shift + command + .

# List
- 类似于 js 的数组
- 有序的，可以 Sorted 和 slice

# Dictionaries
- key-value 跟js的对象很像
- 无须的，不能 sorted 排序
- 但你不需要知道确定的index位置的时候，可以用
```
my_dict = {'key': 'value', 'apple': 2.99, 'k2': [1, 3, 4], 'k3': {'insideKey': 2}}
my_dict['apple'] # 2.99
```
### 获取 所有的 key
```
d = {'k1': 100, 'k2': 200, 'k3', 300}
d.keys()
```
### 获取 所有的 value
```
d = {'k1': 100, 'k2': 200, 'k3', 300}
d.values()
```
### 获取 所有的 item
```
d = {'k1': 100, 'k2': 200, 'k3', 300}
d.items()
```

# upper()
- 大写

# Tuples 元组
```
t = (1, 2, 3)
mylist = [1, 2, 3]
type(t) # tuple
type(mylist) # list
len(t) # 3
```
- 跟 list 一样，可以用 slicing 和 indexing
```
t = ('one', 2)
t[0] # 'one'
t[-1] # 2
```
- tuples内置的方法只有两个， index 和 count
```
t = ('a', 'b', 'a')
t.count('a') # 有多少个 a
t.index('a') # 返回第一次出现的 a 的位置
```
- list 可以改变， tuple 不可改变
```
# list
mylist = [1, 2, 3]
mylist[0] = 'NEW'
mylist # ['NEW', 2, 3]

tuple
t[0] = 'NEW' # 报错
TypeError: 'tuple' object does not support item assignment
```

# Sets
- Sets are unordered collections of unique elements
无序集合，元素唯一
```
a = {1,2,3,4}
type(a) # set

myset = set() # 返回有个空的 set()
myset.add(1) # {1}
myset.add(2) # {1, 2}
```
- 唯一性
```
mylist = [1,1,1,1,1,1,2,2,2,2]
set(mylist) # {1, 2}
```

# Booleans 布尔 True False
- 首字母一定大写
```
type(False) #bool
1 == 1 # True

b = None # b
type(b) # NoneType
```

# Files I/O
- 在jupyter中写文件
```
%%writefile myfile.txt
hello this is a text file
this is the second line
this is the third line

# Writing myfile.txt
```
- 打开存在的文件
`myfile = open('myfile.txt')`
- 打开不存在的文件会报错
```
myfile = open('whoops_wrong.txt')

# FileNotFoundError: [Errno 2] No such file or directory: 'whoops_wrong.txt'
```

> 输入 pwd 查看当前文件路径

### 读取文件
##### read()
```
myfile = open('myfile.txt')
myfile.read() # 返回myfile.txt中的内容 \n 是下一行
```
- 读取第二次的时候，返回空字符串
  jokes:beginners are scratching their heads thinking well what the hell happened

- 重置cursor myfile.seek(0)
- 再读取就没问题了 myfile.read()
**记得，再次读取要重置指针**

##### readlines() 返回一个list 每个元素代表一行
```
myfile.readlines()
```

##### File Locations
windows: `myfile = open('C:\\Users\\UserName\\Folder\\test.txt')`
-双斜线是Python的转义符号
MacOD or Linux: `myfile = open('/Users/YourUserName/Folder/myfile.txt')`

##### 关闭文件 close()
- 当你用pthon打开文件，还想用电脑删除时，会报错，python is still using this file
```
myfile.close()
```
##### 以新文件形式打开
- 关闭不会报错了
```
with open('myfile.txt') as my_new_file:
    contents = my_new_file.read()
```
> jupyter 中 用shift + tab 会提示语法

##### 写入文件
**读写权限**
- mode='r # read only
    只读
- mode='w' # write only(will overwrite files or create new)
    只写(会覆盖或者创建一个新的)
- mode='a' # is append only(will add on to files)
    只可添加(只可以向文件中添加内容)
- mode='r+' # is reading and writing
    读写
- mode="w+" # is writing and reading(Overwrites exising files or creates a new file)
    读写(重新覆盖已经存在的文件或者创建一个新的文件)

读文件
```
with open('myfile.txt', mode="r") as f:
    print(f.read())
```
写文件
```
with open('myfile.txt', mode="a") as f:
    f.write('FOUR ON FOURTH')
```
创建新文件
```
with open('dsfergg.txt', mode="r") as f:
    print(f.read())
```
