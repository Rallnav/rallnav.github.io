# This is the place where used to markdown the python learning.
## Python命名规则：
- 类的名字中的单词首字母都是大写的。(驼峰式camel)

## Python读写文件模式
1.  r 打开只读文件，该文件必须存在。 
2.  r+ 打开可读写的文件，该文件必须存在。 
3.  w 打开只写文件，若文件存在则文件长度清为0，即该文件内容会消失。若文件不存在则建立该文件。 
4.  w+ 打开可读写文件，若文件存在则文件长度清为零，即该文件内容会消失。若文件不存在则建立该文件。 
5.  a 以附加的方式打开只写文件。若文件不存在，则会建立该文件，如果文件存在，写入的数据会被加到文件尾，即文件原先的内容会被保留。 
6.  a+ 以附加方式打开可读写的文件。若文件不存在，则会建立该文件，如果文件存在，写入的数据会被加到文件尾后，即文件原先的内容会被保留。 
7.  上述的形态字符串都可以再加一个b字符，如rb、w+b或ab＋等组合，加入b 字符用来告诉函数库打开的文件为二进制文件，而非纯文字文件。不过在POSIX系统，包含Linux都会忽略该字符。




## 获取脚本路径
### sys.path[0]：获取执行脚本目录绝对路径

#每次执行脚本时，python会将执行脚本目录加入PYTHONPATH环境变量中(sys.path获取)
```
#!/usr/bin/python3

import os
import sys

print(sys.path)
print(sys.path[0])
执行结果：
[root@localhost tmp]# ./py_test1/pytest24.py 
['/tmp/py_test1', '/usr/local/lib/python36.zip', '/usr/local/lib/python3.6', '/usr/local/lib/python3.6/lib-dynload', '/usr/local/lib/python3.6/site-packages', '/usr/local/lib/python3.6/site-packages/pip-9.0.1-py3.6.egg']
/tmp/py_test1
```

### sys.argv[0]：获取脚本执行本身路径；
```
#!/usr/bin/python3

import os
import sys

print(sys.argv[0])
执行1结果：
[root@localhost tmp]# ./py_test1/pytest24.py 　　#相对路径执行脚本则会返回相对路径
./py_test1/pytest24.py
执行2结果：
[root@localhost tmp]# /tmp/py_test1/pytest24.py  #绝对路径执行脚本则返回绝对路径
/tmp/py_test1/pytest24.py
```
注：sys.argv[0]获取得不是脚本目录路径，而是脚本本身执行时的路径！

###__file__：同sys.argv[0]相似，获取脚本执行本身路径：
```
#!/usr/bin/python3

import os
import sys

print("sys.argv[0] Output:",sys.argv[0])
print("__file Output:",__file__)
执行1结果：
[root@localhost tmp]# ./py_test1/pytest24.py   #相对路径执行脚本则会返回相对路径
sys.argv[0] Output: ./py_test1/pytest24.py
__file Output: ./py_test1/pytest24.p

执行2结果：
[root@localhost tmp]# /tmp/py_test1/pytest24.py  #绝对路径执行脚本则会返回绝对路径
sys.argv[0] Output: /tmp/py_test1/pytest24.py
__file Output: /tmp/py_test1/pytest24.py
　　注：__file__获取得不是脚本目录路径，而是脚本本身执行时的路径！
```
### os.path.abspath(__file__)和os.path.realpath(__file__)：获取脚本执行本身的绝对路径
```
　　通过获取__file__路径，然后转换成绝对路径
#!/usr/bin/python3

import os
import sys

print("__file Output:",__file__)
print(os.path.abspath(__file__))
print(os.path.realpath(__file__))
执行结果：
[root@localhost tmp]# ./py_test1/pytest24.py 
__file Output: ./py_test1/pytest24.py
/tmp/py_test1/pytest24.py
/tmp/py_test1/pytest24.py
注：os.path.abspath(__file__)和os.path.realpath(__file__)获取得是脚本本身的绝对路径！
```


[BackToHomepage](https://rallnav.github.io)
