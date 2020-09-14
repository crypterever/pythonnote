# 10.TPYBoard v202 自制微信远程智能温湿度计

## 申请微信推送服务

能否实现微信推送服务的平台有很多，这里我就不一一解释了。我选用了「Server酱」，英文名「ServerChan」。你完全可以选用你认为比较好用的平台。「Server酱」的申请方法：

打开该网址 http://sc.ftqq.com/3.version 开通并使用。

> - 1.登入：用GitHub账号登入网站，点击进入“发送消息”页面，就能获得一个SCKEY。具体见：http://sc.ftqq.com/?c=code
> - 2.绑定：点击“微信推送”页面，扫码关注同时即可完成绑定
> - 3.发消息：往 https://sc.ftqq.com/SCKEY.send 发GET请求，就可以在微信里收到消息啦。

## 让我们开始DIY温湿度计

![image-20200913095244284](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913095244284.png)

## 少不了的编程

TPYBoard v202主要有两个文件来控制，一个是boot,py，一个是main.py。我们只需要修改这两个文件就可以完成程序的编写。如果你对如何使用TPYBoard v202还不清楚，可以参照此教程：http://docs.tpyboard.com/zh/latest/tpyboard/tutorial/v202/start/。

## 编写boot脚本

`boot.py`：

```python
import network
import utime

pdcn = network.WLAN(network.STA_IF)
pdcn.active(True)
pdcn.connect('wifi账号', 'wifi密码')
utime.sleep(5)
if pdcn.isconnected():
    print("WiFi is connected %s."%pdcn.ifconfig()[0])
else:
    pdcn.active(False)
    utime.sleep(5)
    print("WiFi cannot connect.")
```

## 编写main.py脚本

`main.py`：

```python
import urequests
import dht
import machine
from machine import Pin
import time

class AlarmSystem:
    def __init__(self):
        self.d = dht.DHT11(machine.Pin(5))

    def dht11(self):
        try:
            self.d.measure()
            return 'Temp:'+str(self.d.temperature())+'°C---Hum:'+str(self.d.humidity())+'%'

        except:
            return '0'

    def push(self, result):
        title = "TPYBoardv202提示您:注意天气变化保持健康心情"
        content = 'text='+title+'&'+'desp='+result
        url="https://sc.ftqq.com/你的密钥.send?%s" % content
        r = urequests.get(url)
        r.close()

p2=Pin(2,Pin.OUT)
a = AlarmSystem()

def SendData():
    p2.value(not p2.value())
    data_= a.dht11()
    if(data_!='0'):
        print(data_)
        a.push(data_)
    else:
        print('GET Data Fail')

if __name__ == '__main__':

    while True:
        SendData()
        time.sleep(300)
```

## 成果分享

到这里，工作完成，方糖就会给你，你就会看到显示的温湿度了。

<img src="https://gitee.com/zr001/writeimges/raw/master/images/Screenshot_2020-09-13-10-38-02-32.png" alt="Screenshot_2020-09-13-10-38-02-32" style="zoom:50%;" />

