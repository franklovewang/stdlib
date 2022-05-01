## 1 python标准库——random

### 1.1 random标准的主要功能

主要用于生成“伪随机数”

### 代码演示

```python
import random

# 生成随机整数
print(random.randint(1, 100)) ---> 33

# 生成随机奇数（1--100）
print(random.randrange(1, 101, 2)) ---> 19

# 生成随机偶数（1--100）
print(random.randrange(2, 101, 2)) ---> 22

# 生成随机浮点数
print(random.random()) ---> 0.46967029904529756，值范围在0.0~1.0之间

# 生成指定范围的浮点数
print(random.uniform(1.1, 1.8)) ---> 1.7843148985287733

# 非数字类型的随机抽样
targetList = ['a', 'b', 'c', 'd', 'e', 'f']
print(random.choice(targetList)) ---> e，抽取一个样本,不改变原列表

# 抽取指定数量的样本
print(random.sample(targetList, 4)) ---> ['c', 'a', 'f', 'd']，不改变原列表

# 乱序，改变原列表；如果不想改变原列表，可以使用sample方法
targetList = ['a', 'b', 'c', 'd', 'e', 'f']
print(targetList) ---> ['a', 'b', 'c', 'd', 'e', 'f'] 
random.shuffle(targetList)
print(targetList) ---> ['c', 'd', 'b', 'a', 'e', 'f']

```

### 案例演示

```python
# 生成随机字符串，密码中包括字母和数字，可以指定生成字符串的长度
import random, string

def get_random_string(length):
    # 数字长度
    num_len = random.randint(1, length-1)
    # 字母长度
    let_len = length - num_len
	# 随机抽样生成数字序列
    numlist = [random.choice(string.digits) for _ in range(num_len)]
    # 随机抽样生成字母序列
    letterlist = [random.choice(string.ascii_letters) for _ in range(let_len)]
    # 合并序列
    alllist = numlist + letterlist
    # 乱序
    random.shuffle(alllist)
    # 拼接成字符串
    result = "".join(alllist)
    # 返回结果
    return result

if __name__ == '__main__':
    ranString = get_random_string(10)
    print(ranString)

```

