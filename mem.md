# python知识点
### 编程小技巧
##### 1. 链状比较操作符
```
n= 10
result= 1< n< 20
print(result)
# True
result= 1> n<= 9
print(result)
# False
```
##### 2. 打印引入模块的文件路径
```
import threading
import socket
print(threading)
print(socket)
#1- <module ‘threading’ from ‘/usr/lib/python2.7/threading.py’>
#2- <module ‘socket’ from ‘/usr/lib/python2.7/socket.py’>
```

##### 3. 设置调试断点
```
import pdb
pdb.set_trace()
```

###### 4. 开启文件分享
```
# Python 2
python -m SimpleHTTPServer

# Python 3
python3 -m http.server
```

##### 5. 一行代码计算任何数的阶乘
```angular2html
Python 2.x.
result= (lambdak: reduce(int.__mul__,range(1,k+1),1))(3)
print(result)
#-> 6

Python 3.x.
import functools
result= (lambdak: functools.reduce(int.__mul__,range(1,k+1),1))(3)
print(result)
#-> 6
```
##### 6.  一行代码搜索字符串的多个前后缀
```
print(“http://www.google.com”.startswith((“http://”,”https://”)))
print(“http://www.google.co.uk”.endswith((“.com”,”.co.uk”)))
#1-> True
#2-> True
```
##### 7. 不使用循环构造一个列表
```
import itertools
test= [[-1,-2],[30,40],[25,35]]
print(list(itertools.chain.from_iterable(test)))
#-> [-1, -2, 30, 40, 25, 35]
```
