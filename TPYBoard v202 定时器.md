# 6.TPYBoard v202 定时器

## 实现方法

**增加一个执行一次的定时器**

> ```python
> from machine import Timer
> tim = Timer(-1)  #新建一个虚拟定时器
> #此处执行时程序会等待5秒打印1，period=5000 以毫秒为单位，mode=Timer.ONE_SHOT 表示只执行一次，callback绑定回调函数
> tim.init(period=5000, mode=Timer.ONE_SHOT, callback=lambda t:print(1))
> ```

**增加一个循环定时器**

> ```python
> from machine import Timer
> tim = Timer(-1)  #新建一个虚拟定时器
> #此方法执行时系统会每隔两秒无限打印2,periodic表示无限打印
> tim.init(period=2000, mode=Timer.PERIODIC, callback=lambda t:print(2))
> ```

## 硬件实物

![image-20200911215433645](https://gitee.com/zr001/writeimges/raw/master/images/image-20200911215433645.png)

## **硬件接线图**

| TPYBoard v202 | DHT11温湿度模块 |
| ------------- | --------------- |
| 5V            | VCC             |
| G4            | DATA            |
| GND           | GND             |

- 连接完成后，将下面代码写进TPYBoard v202即可读取当前温湿度的值，下面是源代码:

  - `main.py`：

    - ```python
      from machine import Timer
          import dht
          import machine
      
      d=dht.DHT11(machine.Pin(4))
      
          def f(t):
            d.measure()
            a=d.temperature()
            b=d.humidity()
            print('温度:',a,'°C')
            print('湿度:',b,'%')
      
          tim = Timer(-1)  #新建一个虚拟定时器
          tim.init(period=2000, mode=Timer.PERIODIC, callback=f)
      ```

- 使用`TPYBoard v202`开发工具-MFU，就可以看到每隔`2`秒钟就会打印一次温湿度数据。若想做一下扩展，可将温湿度显示到OLED显示屏上，这样一个小型的`DIY`温湿度检测仪就诞生了。

## TPYBoard v202 常见问题及使用技巧

> `TPYBoard v202`采用`ESP8266-12 E/12F`作为主控模块。
>
> - Flash大小：32Mbit（4MBit）
> - 温度范围：-20～80°C
> - 天线封装：PCB
> - 工作电压：3.0～3.6V（建议3.3V）
> - 指示灯IO口：GPIO2
> - 默认波特率：115200

## 支持语言

TPYBoard v202完美支持MicroPython使用Python语言开发，同时兼容NodeMCU也可以使用Lua语言。

## 接口种类

TPYBoard v202接口类型有：SPI接口1个、IIC接口1个、ADC接口1个、UART 接口 1个。

## 如何使用串口

源码：

```python
from machine import UART
u2=UART(0,115200)#串口初始化
u2.readall()#读取串口全部数据
u2.write(‘hello’)#写入串口数据
```

## 固件的烧写与擦除

若因为一些操作或意外，导致v202不能正常工作时，可尝试重新烧写固件试试，如果不起作用的话，可以先进行擦除在烧写。

[点击查看固件擦除教程](http://docs.tpyboard.com/zh/latest/tpyboard/tutorial/v202/firmwipe/)

[点击查看固件烧写教程](http://docs.tpyboard.com/zh/latest/tpyboard/tutorial/v202/firmware/)

## 调试工具

v202通过数据线接入电脑后，会安装一个`COM`串口，这个可以在电脑的设备管理器中看到，如：

因为在v202开发板上加载了CH340（USB转串口）芯片，所以我们只要使用一个支持串口功能终端的软件即可。本人比较推荐的调试工具是Putty。

Putty下载地址:

http://tpyboard.com/download/tool/3.html

若有的小伙伴的电脑不能自动安装CH340驱动的话，这里提供一个下载地址，可自行进行安装。

下载地址：http://tpyboard.com/download/drive/163.html

## 下载程序的工具

- TPYBoard v202不像是TPYBoard v102系列的一样，可以自动在电脑上加载一个磁盘，代码文件直接拷贝到磁盘中就可以运行。

- TPYBoard v202需要文件下载工具才能将代码下载到Flash内运行。

  网上比较流行有两种工具 

  - `ESPlorer` 它是用`Java`开发的，使用前需要安装`Java`运行库，支持`Windows`、`Linux`和`Mac OS`多种系统平台；
    [ESPlorer](http://tpyboard.com/download/tool/170.html)
  - `MicroPython File Uploader` 它是用doNET开发的，只支持`Windows`系统平台。本人比较推荐`MicroPython File Uploader`，虽然他没有ESPlorer的功能强大，但它是一个小巧快速的ESP8266文件上传工具，上传文件快，同时也支持Putty中调试的功能。
    [MicroPython File Uploader](http://tpyboard.com/download/tool/170.html)

## PWM控制舵机

### 准备工作：

- TPYBoard v202 1块
- micro USB数据线 1条
- SG90舵机 1个
- MicroPython File Uploader [点击下载](http://www.tpyboard.com/download/tool/170.html)