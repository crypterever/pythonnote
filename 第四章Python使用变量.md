# 第四章使用变量

> ![image-20200920161757074](https://gitee.com/zr001/writeimges/raw/master/images/image-20200920161757074.png)

## 4.1Python名称

- 名称必须以字母或下划线(_)开头，可包含字母、数字、下划线。
- 区分大小写
- 命名方法
	- 骆驼式命名法
	- 普通命名法

## 4.2动手练习

### 创建Self-Timer(自我控时)生日聚会游戏

```python
# EG4-01 Self Timer

import time
import random

print('Welcome Self Timer')
print()
print('Everybody stand up')
print('Stay standing until you think the time has ended')
print('Then sit down.')
print('Anyone still standing when the time ends loses.')
print('The last person to sit down before the time ended will win')

stand_time = random.randint(5,20) # 获得一个随机站立时间值并存储它
print('Stay standing for',)

```

### 显示语句中的单引号和双 引号

- 使用三引号