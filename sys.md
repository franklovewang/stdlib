## 1 python标准库——sys

### 1.1 sys标准库的主要功能

针对python解释器相关的变量和方法

###  1.2 变量

```python
import sys
# version: 解释器的版本
print(sys.version) ---> 3.7.2 (tags/v3.7.2:9a3ffc0492, Dec 23 2018, 22:20:52) [MSC v.1916 32 bit (Intel)]

# maxsize: 能够表示的最大int
print(sys.maxsize) ---> 2147483647

# path: 环境变量
print(sys.path) ---> ['D:\\python_learning\\str_format', 'D:\\python_learning', 'C:\\dev\\python\\Python37\\python37.zip', 'C:\\dev\\python\\Python37\\DLLs', 'C:\\dev\\python\\Python37\\lib', 'C:\\dev\\python\\Python37', 'C:\\dev\\python\\Python37\\lib\\site-packages']

# platform：操作系统版本
print(sys.platform) ---> win32

# copyright: 版权信息
print(sys.platform)

# argv: 参数
print(sys.argv) ---> ['D:/python_learning/str_format/demo3.py']

python demo3.py 1 ---> ['demo3.py', '1']
```

### 1.3 方法

```python
# exit(): 退出，有个状态码
sys.exit(1) ---> Process finished with exit code 1

# getdefaultencoding()：默认字符编码集
print(sys.getdefaultencoding()) ---> utf-8

# getfilesystemencoding(): 获取文件字符编码集
print(sys.getfilesystemencoding()) ---> utf-8

# 获取最大递归次数
print(sys.getrecursionlimit()) ---> 1000

# 修改递归次数
sys.setrecursionlimit(200)
print(sys.getrecursionlimit()) ---> 200
```

