# 第二章 Python 和编程

## 2.1编程人员的工作

- 只有你能自行解决问题，此后才能编写程序完成任务
- 必须让计算机理解你需要干啥

> 要创建程序，必须拿出一个解决方案，然后将其分解成多个简单步骤，使得计算机可以执行

### 2.1.1 编程和问题

`编程`=`管道工`

> 在解决问题前，有一个有关问题的严密定义
>
> 功能设计规范`FDS` `Functional Design Specification`
>
> 每次编写程序时，都首先写好周密的规范。即使帮朋友办事，也照写不误，标准丝毫不差，甚至更高。

### 2.1.2程序用于处理数据

![image-20200916194733112](https://gitee.com/zr001/writeimges/raw/master/images/image-20200916194733112.png)

![image-20200916194826316](https://gitee.com/zr001/writeimges/raw/master/images/image-20200916194826316.png)

> `输入`文本为黑色，`Python输出`显示为蓝色，`命令提示`显示为褐色，`错误消息`显示为红色

## 2.2使用Python函数

### 2.2.1ord函数

> [ord]() 即 [ordinal value]()
>
> 提供字符对应的`数值`
>
> ![image-20200916200047577](https://gitee.com/zr001/writeimges/raw/master/images/image-20200916200047577.png)



### 2.2.2chr函数

> 与`ord`函数作用相反

### 2.2.3使用bin函数

![image-20200916200632808](https://gitee.com/zr001/writeimges/raw/master/images/image-20200916200632808.png)

`bin`函数返回一个字符串，该字符串是相应数值的二进制表示形式。字符串开头的`0b`告诉读者，这是数值的二进制表示形式。

### 2.2.4动手练习

```python
ord('A')
65
ord(' ')
32
```

