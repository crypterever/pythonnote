# 11.TPYBoard v202 MQTT协议1:接入OneNET云平台

## 物联网（Internet    of    Things，缩写LOT）

是基于互联网、传统电信网等信息承载体，让所有能行使独立功能的普通物体实现互联互通的网络。其应用领域主要包括运输和物流、工业制造、健康医疗、智能环境（家庭、办公、工厂）等，具有十分广阔的市场前景。

物联网的概念最早是在1999年由Kevin Ashton在一次演讲中提出来的，当时他是一个RFID研究机构的执行主任，这家研究机构是在宝洁公司和吉列公司的赞助下成立的。而他本人也因此被称为物联网之父。随后麻省理工学院的Neil Gershenfeld教授出版了一本名为`《When things Start to Think》`的书。以这些为标志，正式揭开了物联网的序幕。

物联网的英文是Internet of Things，缩写为IoT。这里的“物”指的是我身边一切能与网络联通的物品。例如你带的手表、你骑的共享单车、马路上的汽车、家里的冰箱、路边的路灯、甚至是一棵树。只要一件物品能够与网络相连，它就都是物联网中的“物”。而所谓物联网，就是“物”与人，以及“物”与“物”之间，通过网络来传递和处理信息。

![image-20200913122429930](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913122429930.png)

物联网的基本特征从通信对象和过程来看，物与物、人与物之间的信息交互是物联网的核心。物联网的基本特征可概括为整体感知、可靠传输和智能处理 。整体感知—可以利用射频识别、二维码、智能传感器等感知设备感知获取物体的各类信息。可靠传输—通过对互联网、无线网络的融合，将物体的信息实时、准确地传送，以便信息交流、分享。

智能处理—使用各种智能技术，对感知和传送到的数据、信息进行分析处理，实现监测与控制的智能化。根据物联网的以上特征，结合信息科学的观点，围绕信息的流动过程，可以归纳出物联网处理信息的`功能`:

(1)`获取信息的功能`。主要是信息的感知、识别，信息的感知是指对事物属性状态及其变化方式的知觉和敏感；信息的识别指能把所感受到的事物状态用一定方式表示出来。

(2)`传送信息的功能`。主要是信息发送、传输、接收等环节，最后把获取的事物状态信息及其变化的方式从时间(或空间)上的一点传送到另一点的任务，这就是常说的通信过程。

(3)`处理信息的功能`。是指信息的加工过程，利用已有的信息或感知的信息产生新的信息，实际是制定决策的过程。

(4)`施效信息的功能`。指信息最终发挥效用的过程，有很多的表现形式，比较重要的是通过调节对象事物的状态及其变换方式，始终使对象处于预先设计的状态 。

![image-20200913122532941](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913122532941.png)

## **OneNET平台**

是由中国移动打造的PaaS物联网开放平台。平台能够帮助开发者轻松实现设备接入与设备连接，快速完成产品开发部署，为智能硬件、智能家居产品提供完善的物联网解决方案。OneNET平台作为连接和数据的中心，能适应各种传感网络和通信网络，将面向智能家居、可穿戴设备、车联网、移动健康、智能创客等多个领域开放。

 

中移OneNET，将数据传输协议、数据储存格式等中间层的东西标准化，形成一个统一、开源的设备云平台，标准化、简约化、集成化，减少企业负担的同时为下一阶段的大数据分析提供基础条件。

 

核心能力输出

OneNET作为设备连接和数据的中心，面向物联网产业上下游企业提供标准化接入和定制化开发，具体能力输出包含2个方面：

1. `硬件侧`：平台适配各种网络环境、兼容国内外主流通信协议，定制化支撑私有通信协议，以及完备的SDK包，可支持各类传感器和智能硬件的快速接入和可控触发控制；还提供对智能硬件的网络状态、终端状态、流量情况、位置信息进行全面的管理和监控；

2. `软件侧`：平台通过丰富的API、应用孵化器、轻应用行业模板支持各类智能硬件和行业应用的图形化展示、SaaS层软件开发，满足物联网领域数据存储、数据安全、大数据分析等平台级服务需求。

OneNET平台在提供设备连接服务和数据中心服务的基础上进行开放合作，面向智能硬件创客和创业型企业推出硬件社区服务（包括硬件集市、双创云等），以及数据展现、数据分析和应用生成服务；面向重点行业领域/大客户推出行业PaaS服务和提供行业应用定制化开发服务。

`IoT PaaS基础能力`：提供智能设备自助开发工具、后台技术支持服务、物联网专网、短彩信、位置定位、设备管理、消息分发、远程升级等基础服务

`SaaS业务服务`：提供第三方应用开发平台，快速实现不同业务需求，借助轻应用孵化器快速搭建Web和APP应用 

`IoT数据云`：提供高扩展的数据库、实时数据处理、智能预测离线数据分析、数据可视化展示等多维度的业务运营服务

`开发者社区`：高频的开发者社区，汇聚着不同的知识源，集合更多的物联网爱好者，让项目与开发成果开始传播

![image-20200913122849193](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913122849193.png)

![image-20200913122558566](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913122558566.png)

![image-20200913122906773](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913122906773.png)

## 什么是MQTT协议

早在1999年，IBM的Andy Stanford-Clark博士以及Arcom公司ArlenNipper博士发明了MQTT（Message Queuing Telemetry Transport，消息队列遥测传输）技术 。MQTT（Message Queuing Telemetry Transport，消息队列遥测传输）是IBM开发的一个即时通讯协议，有可能成为物联网的重要组成部分。该协议支持所有平台，几乎可以把所有联网物品和外部连接起来，被用来当做传感器和致动器（比如通过Twitter让房屋联网）的通信协议。

## 实验准备

- 硬件材料
  - TPYBoard v202
  - 面包板
  - 数据线
  - LED发光二极管
  - ![image-20200913104346273](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913104346273.png)

- 软件准备

  - [MicroPython File Uploader](http://www.tpyboard.com/download/tool/170.html)用于与开发板的文件传输	

  - 第三方库文件： [micropython-libumqtt.simpleumqttsimple.py](http://www.tpyboard.com/download/data/184.html)
  - 下载之后的库文件放在`E:\idmdownload\micropython-lib\umqtt.simple\umqtt`

  - [OneNET](https://open.iot.10086.cn/)平台创建MQTT协议的产品并添加设备。
  - 登录成功进入开发者中心，添加一个新产品。
  - 创建产品![addp](https://gitee.com/zr001/writeimges/raw/master/images/addp.gif)
  - 新建设备![addd](https://gitee.com/zr001/writeimges/raw/master/images/addd.gif)
  - ![image-20200913112235961](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913112235961.png)

## 编写程序

`boot.py`：

```python
#连接本地网络
def do_connect():
    import network
    sta_if = network.WLAN(network.STA_IF)
    ap_if = network.WLAN(network.AP_IF)
    if ap_if.active():
        ap_if.active(False)
    if not sta_if.isconnected():
        print('connecting to network...')
    sta_if.active(True)
    sta_if.connect('winnerzr','12345678') #wifi的SSID和密码
    while not sta_if.isconnected():
        pass
    print('network config:', sta_if.ifconfig())
do_connect()
```

> 修改`mqtt.py`中设备ID、产品ID和APIKEY参数的信息。
>
> ![set](https://gitee.com/zr001/writeimges/raw/master/images/set.gif)

`mqtt.py`：

```python
from simple import MQTTClient
from machine import Pin
import machine
import micropython
#选择G4引脚
g4 = Pin(4, Pin.OUT, value=0)
# MQTT服务器地址域名为：183.230.40.39,不变
SERVER = "183.230.40.39"
#设备ID
CLIENT_ID = "deviceID"
#随便起个名字
TOPIC = b"TurnipRobot"
#产品ID
username='productID'
#产品APIKey:
password='APIKey'
state = 0
def sub_cb(topic, msg):
    global state
    print((topic, msg))
    if msg == b"on":
        g4.value(1)
        state = 1
        print("1")
    elif msg == b"off":
        g4.value(0)
        state = 0
        print("0")
    elif msg == b"toggle":# 切换状态
        state = 1 - state
        g4.value(state)

def main(server=SERVER):
    #端口号为：6002
    c = MQTTClient(CLIENT_ID, server,6002,username,password)
    c.set_callback(sub_cb)
    c.connect()
    c.subscribe(TOPIC)
    print("Connected to %s, subscribed to %s topic" % (server, TOPIC))
    try:
        while 1:
            c.wait_msg()
    finally:
        c.disconnect()
```

`main.py`：

```python
import mqtt
mqtt.main()
```

修改`mqtt.py`中设备`ID`、产品`ID`和`APIKEY`参数的信息

![ddsssdgds](https://gitee.com/zr001/writeimges/raw/master/images/ddsssdgds.gif)

连接成功：

- ![image-20200913124223244](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913124223244.png)
- ![image-20200913131152841](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913131152841.png)

- ![12123324vfffs](https://gitee.com/zr001/writeimges/raw/master/images/12123324vfffs.jpg)
- ![image-20200913130616573](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913130616573.png)

