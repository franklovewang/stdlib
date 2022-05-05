## 1 python标准库——logging

### 1.1 日志处理方式

![](../../Typora_images/85.png)

### 1.2 logging库日志级别

![](../../Typora_images/86.png)

默认日志级别是warning

### 1.3 logging的高级应用

logging模块采用了模块化设计，主要包含四种组件：

Loggers：记录器，提供应用程序代码直接使用的接口

Handlers：处理器，将记录器产生的日志发送至目的地

Filters：过滤器，提供更好的粒度控制，决定哪些日志会被输出

Formatters：格式化器，设置日志内容的组成结构和消息字段

### 1.4 案例演示

```python
import logging
# 默认日志级别为warning
# 使用baseConfig()来指定日志输出级别，默认输出到控制台上
logging.basicConfig(level=logging.DEBUG)
logging.debug('This is debug log') ---> DEBUG:root:This is debug log
logging.info('This is info log') ---> INFO:root:This is info log
logging.warning('This is warning log') ---> WARNING:root:This is warning log
logging.error('This is error log') ---> ERROR:root:This is error log
logging.critical('This is critical log') ---> CRITICAL:root:This is critical log
        
# 将日志输出到文件中，默认是以追加的模式
logging.basicConfig(filename='run.log', level=logging.DEBUG)
logging.debug('This is debug log')
logging.info('This is info log')
logging.warning('This is warning log')
logging.error('This is error log')
logging.critical('This is critical log')

# 将日志输出到文件中
logging.basicConfig(filename='run.log', filemode='w', level=logging.DEBUG)
logging.debug('This is debug log')
logging.info('This is info log')
logging.warning('This is warning log')
logging.error('This is error log')
logging.critical('This is critical log')
```

