# 9.TPYBoard v202 通过HTTP协议上传温湿度数据

> `TPYBoard_V202`是以遵照`MIT`许可的`MicroPython`为基础，由`TurnipSmart`公司制作的一款`MicroPython`开发板，它基于`ESP8266`，通过`USB`接口进行数据传输,可在`3.5V-6V`之间的电压正常工作。让您零基础也能灵活掌握`8266`模块通信技术！支持`Python`语言的WiFi通信开发板。

## 所需原件

- TPYBoardV202开发板 一块
- DHT11模块 一个
- 杜邦线 若干

## DHT11介绍

`DHT11`数字温湿度传感器是一款含有已校准数字信号输出的`温湿度复合传感器`，它应用专用的数字模块采集技术和温湿度传感技术，确保产品具有极高的可靠性和卓越的长期稳定性。传感器包括一个电阻式感湿元件和一个`NTC`测温元件，并与一个高性能8位单片机相连接。因此该产品具有品质卓越、超快响应、抗干扰能力强、性价比极高等优点。每个`DHT11`传感器都在极为精确的湿度校验室中进行校准。校准系数以程序的形式存在`OTP`内存中，传感器内部在检测信号的处理过程中要调用这些校准系数。单线制串行接口，使系统集成变得简易快捷。超小的体积、极低的功耗，使其成为该类应用中，在苛刻应用场合的最佳选择。

对`DHT11`做了简要介绍，下面再介绍一个这个器件在`V202`开发板上的使用方法，这个器件的使用方法就简单了，主要是因为`v202`开发板里面集成了`DHT`的类库，你在使用`DHT11`的时候，直接声明一下类库，调用函数，读取数值就可以了。

## 制作主要过程

![过程](https://gitee.com/zr001/writeimges/raw/master/images/1493349856713838.png)

![image-20200912165631230](https://gitee.com/zr001/writeimges/raw/master/images/image-20200912165631230.png)

## 制作流程

DHT11模块上面有三根针脚，分别为GND,VCC,OUT，接线对应如下表：

![image-20200912165724167](https://gitee.com/zr001/writeimges/raw/master/images/image-20200912165724167.png)

（1）按照上表接好线后，我们开始编辑`main.py`的代码；

（2）首先需要声明我们所用到的类库，例如引脚，时间，接口，这个实验里面我们好用到了网络，机制等等；

（3）在我们声明类库完成之后，我们需要进行类库函数的调用，这里我们需要调用的是`DHT11`读取数据的函数；

（4）完成上面的基本准备工作后，需要定义两个我们会用到的函数，简单的说就是开发板连接路由器函数和开发板数据上传函数；

（5）完成开发板连接路由器的函数后，调用一下这个函数，这个函数在这次的代码中仅使用一次；

（6）接下来建立起整个代码的主循环；

（7）在循环中，调用`DHT`类库中数据测量的函数，随后在函数中读取出温度和湿度的数值，并保存；

（8）获取到温湿度后，开始调用之前定义好的开发板数据上传函数，把数据上传至服务器；

（9）延时一段时间，在整个循环中不断的读取温湿度，就完成了实时的温湿度监控。

`main.py`：

> ```python
> import dht
> import machine
> import network
> from machine import Pin
> import socket
> import urllib
> import time#声明用到的类库，尤其是dht的类库
> 
> d = dht.DHT11(machine.Pin(5))#声明用到类库中的函数，并设置参数
> led = Pin(2, Pin.OUT)
> count=0
> def http_get(url):#定义数据上传的函数
>  _, _, host, path = url.split('/', 3)#分割传进来的参数
>  addr = socket.getaddrinfo(host, 80)[0][-1]#把传进来的参数处理成符合格式的地址
>  s = socket.socket()
>  s.connect(addr)#链接地址
>  s.send(bytes('GET /%s HTTP/1.0\r\nHost: %s\r\n\r\n' % (path, host), 'utf8'))#向链接的地址发送数据
>  while True:#开始数据发送
>      data = s.recv(50)
>      if data:#数据未发送完成，继续发送
>          recive=str(data, 'utf8').upper()
>          #print(str(data, 'utf8'), end='')
>          if(recive.find('YES')>-1):
>              print('Send Data OK')
>      else:#数据发送完成，退出while
>          break
>  s.close()#关闭数据连接
> def do_connect():#定义开发板连接无线网络的函数
>  wlan = network.WLAN(network.STA_IF)#设置开发板的网#络模式
>  wlan.active(True)#打开网络连接
>  if not wlan.isconnected():#判断是否有网络连接
>      print('connecting to network...')
>      wlan.connect('无线名称', '密码')#设置想要连接的无线名称和密码
>      while not wlan.isconnected():#等待连接上无线网络
>          pass
>  print('network config:', wlan.ifconfig())
> 
> do_connect()#调用一次开发板连接无线网络的函数
> while True:#开始整个代码的大循环
>  d.measure()#调用DHT类库中测量数据的函数
>  temp_=str(d.temperature())#读取measure()函数中的温度数据
>  hum_=str(d.humidity())#读取measure()函数中的湿度数据
>  count+=1#计数变量+1
>  print('eg:',temp_,'-',hum_)
>  http_get('http://old.tpyboard.com/esp8266/SensorTest.php?t='+temp_+'&h='+hum_+'')
>  #调用数据上传函数，把最新测量得到的数据进行上传
>  print('Count:',count)
>  time.sleep(5)
> ```
>
> - [点击查看上传的数据](http://old.tpyboard.com/esp8266/SensorData.php)
> - [下载源码](https://github.com/TPYBoard/TPYBoard-v202)