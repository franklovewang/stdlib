## 1 python标准库——datetime

### 1.1 datetime标准库的类

- datetime.date：表示日期的类
- datime.time：表示时间的类
- datetime.datetime：表示时间日期的类
- datetime.timedelta：表示两个datetime对象的差值
- datetime.tzinfo：表示时区的相关信息

### 1.2 datetime.date类

```python
import time
import datetime

# 生成日期
d = datetime.date(2022, 3, 24)
print(d, type(d)) ---> 2022-03-24 <class 'datetime.date'>

d = datetime.date.today()
print(d, type(d)) ---> 2022-05-21 <class 'datetime.date'>

d = datetime.date.fromtimestamp(time.time())
print(d, type(d)) ---> 2022-05-21 <class 'datetime.date'>

# 类属性
print(datetime.date.max) ---> 9999-12-31
print(datetime.date.min) ---> 0001-01-01
print(datetime.date.resolution) ---> 1 day, 0:00:00
        
# 实例属性
print(d.year) ---> 2022
print(d.month) ---> 5
print(d.day) ---> 21

# 常用的实例方法
# datetime.date对象 ——> 结构化时间对象
print(d.timetuple()) ---> time.struct_time(tm_year=2022, tm_mon=5, tm_mday=21, tm_hour=0, tm_min=0, tm_sec=0, tm_wday=5, tm_yday=141, tm_isdst=-1)

# 其他方法
# replace
print(d.replace(2023)) ---> 2023-05-21
# toordinal
print(d.toordinal()) ---> 738296（从0001-01-01到现在的天数）
# weekday
print(d.weekday()) ---> 5（0代表周一，6代表周日）
# isoweekday
print(d.isoweekday()) ---> 6(1代表周一，0代表周日)
# isoformat等同于默认输出格式
print(d.isoformat()) ---> 2022-05-21
# strftime:自定义格式
print(d.strftime('%Y/%m/%d')) ---> 2022/05/21
```

### 1.3 datetime.time类

```python
import datetime
# 生成时间
t = datetime.time(15, 22, 34, 777777)
print(t, type(t)) ---> 15:22:34.777777 <class 'datetime.time'>
        
# 类属性
print(datetime.time.min) ---> 00:00:00
print(datetime.time.max) ---> 23:59:59.999999
print(datetime.time.resolution) ---> 0:00:00.000001
        
# 实例属性
print(t.hour) ---> 15
print(t.minute) ---> 22
print(t.second) ---> 34
print(t.microsecond) ---> 777777

# 实例方法
# isoformat
print(t.isoformat()) ---> 15:22:34.777777
# strftime
import locale
locale.setlocale(locale.LC_CTYPE, 'chinese')
print(t.strftime('%H时%M分%S秒 %f微妙')) ---> 15时22分34秒 777777微妙
```

### 1.4 datetime.datetime类

```python
# 生成日期时间
# 通过构造器生成日期时间
dt = datetime.datetime(2022, 3, 24, 22, 33, 45, 888888)
print(dt, type(dt)) ---> 2022-03-24 22:33:45.888888 <class 'datetime.datetime'>
# today: 获取今天的日期时间       
dt = datetime.datetime.today()
print(dt, type(dt)) ---> 2022-05-22 21:53:29.829444 <class 'datetime.datetime'>
# now:获取日期时间。可以传入tz，获取对应时区的日期时间。
dt = datetime.datetime.now(tz=None)
print(dt, type(dt)) ---> 2022-05-22 21:55:03.065001 <class 'datetime.datetime'>
# 获取格林威治日期时间
dt = datetime.datetime.utcnow()
print(dt, type(dt)) ---> 2022-05-22 13:56:58.538425 <class 'datetime.datetime'>   
# timestamp ——> locale dt
dt = datetime.datetime.fromtimestamp(time.time())
print(dt, type(dt)) ---> 2022-05-22 22:01:08.804764 <class 'datetime.datetime'>
# timestamp ——> utc dt
dt = datetime.datetime.utcfromtimestamp(time.time())
print(dt, type(dt)) ---> 2022-05-22 14:02:31.135148 <class 'datetime.datetime'>
# 字符串 ——> dt
dt = datetime.datetime.strptime('2022-05-22 11:11:11', '%Y-%m-%d %H:%M:%S')
print(dt, type(dt)) ---> 2022-05-22 11:11:11 <class 'datetime.datetime'>
        
# date,time --> dt
d = datetime.date.today()
t = datetime.time(22, 15, 24, 666666)
dt = datetime.datetime.combine(d, t)
print(dt, type(dt)) ---> 2022-05-22 22:15:24.666666 <class 'datetime.datetime'>

# 实例属性
print(dt.year)
print(dt.month)
print(dt.day)
print(dt.hour)
print(dt.minute)
print(dt.second)
print(dt.microsecond)

# 实例方法
# replace
print(dt.replace(year=2028)) ---> 2028-05-22 22:15:24.666666
        


```





