# 4.TPYBoard v202 Network连接网络

- **Network库的使用方法**

- 网络模块用于配置`WiFi`连接。一共两种模式，模式一:是TPYBoard v202当`STA`节点，即连接路由器的节点。模式二，是TPYBoard v202做为`AP`，充当路由.

- **TPYBoard v202 STA节点模式**

  - ```python 
    import network
    wlan = network.WLAN(network.STA_IF)      # 创建一个站（当ESP8266连接到路由器时）接口
    wlan.active(True)                        # 激活接口
    wlan.scan()                              # 扫描接入点
    wlan.isconnected()                       # 检查站点是否连接到路由器
    wlan.connect('essid', 'password')        # 连接到路由器,设置名称密码
    wlan.config('mac')      # 获取接口的MAC地址
    wlan.ifconfig()         # 获取接口的IP / netmask / gw / DNS地址
    
    #检查是否连接是否建立
    wlan.isconnected()
    #检查接口是否活动
    wlan.active()
    #检查接口的网络设置
    wlan.ifconfig()
    ```

- **TPYBoard v202自动连接本地网络:**

  - ```python
    from machine import Pin
    import network
    import time
    def led_state():
        p2 = Pin(2, Pin.OUT)
        p2.value(0) # 点亮LED
        time.sleep_ms(500)
        p2.value(1) # 熄灭LED
        time.sleep_ms(500)
        p2.value(0) # 点亮LED
        time.sleep_ms(500)
        p2.value(1) # 熄灭LED
        time.sleep_ms(500)
    def do_connect():
        sta_if = network.WLAN(network.STA_IF)
        p2 = Pin(2, Pin.OUT)
        sta_if.active(False)
        if not sta_if.isconnected():
            p2.value(0)
            print('connecting to network...')
            sta_if.active(True)
            sta_if.connect('TurnipSmart', 'turnip2016')
            while not sta_if.isconnected():
                pass
        if sta_if.isconnected():
            print('connect success')
            led_state()
            print('network config:', sta_if.ifconfig())
    do_connect()
    ```

- **TPYBoard v202 AP模式**

  - ```python
    import network
    ap = network.WLAN(network.AP_IF) ＃创建接入点接口
    ap.active(True)         # 激活接口
    ap.config(essid='ESP-AP',password='123456') # 设计接入点的ESSID，密码为123456
    ```

- 也可以设置无密码开放模式，如下：

  ```python
  ap.config(essid='ESP-AP',authmode=0) # 设计接入点的ESSID，开放无密码模式
  ```

- AuthMode有五种模式：

  - 0 : OPEN
  - 1 : WEP
  - 2 : WPA-PSK
  - 3 : WPA2-PSK
  - 4 : WPA/WPA2-PSK

## 实验一

- 实验要求：

  - 当`TPYBoard v202`未连接到网络时，LED亮起警示，当连接成功后，熄灭。

    `main.py`程序代码：

    ```python
    import network
    from machine import Pin
    sta_if = network.WLAN(network.STA_IF)
    p2 = Pin(2, Pin.OUT)
    #我们在这里把接入点接口禁用，方便观看实验效果，非实验可以去掉
    sta_if.active(False)
    if not sta_if.isconnected():
            p2.value(0)
            print('connecting to network...')
            sta_if.active(True)
            sta_if.connect('TurnipSmart', 'turnip2016')
            while not sta_if.isconnected():
                    pass
    if sta_if.isconnected():
            print('connect success')
            p2.value(1)
            print('network config:', sta_if.ifconfig())
    ```

- 实验要求：

  - ```python
    import network
    from machine import Pin
    sta_if = network.WLAN(network.STA_IF)
    p2 = Pin(2, Pin.OUT)
    #我们在这里把接入点接口禁用，方便观看实验效果，非实验可以去掉
    sta_if.active(False)
    if not sta_if.isconnected():
            p2.value(0)
            print('connecting to network...')
            sta_if.active(True)
            sta_if.connect('TurnipSmart', 'turnip2016')
            while not sta_if.isconnected():
                    pass
    if sta_if.isconnected():
            print('connect success')
            p2.value(1)
            print('network config:', sta_if.ifconfig())
    ```

## 实验二

- 实验要求

  - 当`TPYBoard v202`连接网络成功后，通过`get`方式向网址 [test](http://old.tpyboard.com/esp8266/test.php) 发起请求，带有一个参数`val`。 网站接收到请求后，判断参数`val`的值是否等于字符A，等于的话返回`begin`，反之返回`error`。`TPYBoard v202`收到`begin`后LED快闪2次。

  - 发起HTTP GET请求的简单方法

    - ```python 
      def http_get(url):
              _, _, host, path = url.split('/', 3)
              addr = socket.getaddrinfo(host, 80)[0][-1]
              s = socket.socket()
              s.connect(addr)
              s.send(bytes('GET /%s HTTP/1.0\r\nHost: %s\r\n\r\n' % (path, host), 'utf8'))
              while True:
                      data = s.recv(100)
                      if data:
                              print(str(data, 'utf8'), end='')
                      else:
                              break
              s.close()
      ```

  - `main.py`程序代码

    - ```python 
      import network
      from machine import Pin
      import socket
      import urllib
      import time
      
      def led_state():
              p2 = Pin(2, Pin.OUT)
              p2.value(0)
              time.sleep_ms(500)
              p2.value(1)
              time.sleep_ms(500)
              p2.value(0)
              time.sleep_ms(500)
              p2.value(1)
      
      def do_connect():
              sta_if = network.WLAN(network.STA_IF)
              p2 = Pin(2, Pin.OUT)
              sta_if.active(False)
              if not sta_if.isconnected():
                      p2.value(0)
                      print('connecting to network...')
                      sta_if.active(True)
                      sta_if.connect('essid', 'pwd')
                      while not sta_if.isconnected():
                              pass
              if sta_if.isconnected():
                      print('connect success')
                      p2.value(1)
                      print('network config:', sta_if.ifconfig())
      
      def http_get(url):
              _, _, host, path = url.split('/', 3)
              addr = socket.getaddrinfo(host, 80)[0][-1]
              s = socket.socket()
              s.connect(addr)
              s.send(bytes('GET /%s HTTP/1.0\r\nHost: %s\r\n\r\n' % (path, host), 'utf8'))
              while True:
                      data = s.recv(50)
                      if data:
                              recive=str(data, 'utf8')
                              #print('recive:',recive)
                              print(str(data, 'utf8'), end='')
                              if(recive.find('begin')>-1):
                                 led_state()
                      else:
                              break
              s.close()
      do_connect()
      http_get('http://old.tpyboard.com/esp8266/test.php?val=A')
      ```
