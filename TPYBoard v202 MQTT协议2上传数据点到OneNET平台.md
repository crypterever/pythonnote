# 12.TPYBoard v202 MQTT协议2:上传数据点到OneNET平台

- 实验准备
  - TPYBoard v202开发板
  - USB数据线
  - NotePad ++ 软件（其他编辑工具也可以）
  - MicroPython File Uploader（MFU）软件
- 在数据点上报之前，我们需要在OneNET云平台上添加一个数据流模板。步骤如下：
  - ![image-20200913131934531](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913131934531.png)
  - ![image-20200913132238757](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913132238757.png)
  - ![image-20200913132258576](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913132258576.png)
- 上传数据点接下来就要进行数据点的上传了。上传数据点时需要参考协议规则说明，大家可以去OnetNET平台文档中心上下载，OnetNET平台文档中心地址：https://open.iot.10086.cn/doc/art431.html#118。 找到[1.1 说明文档]找到关于MQTT项目中的设备终端接入协议-MQTT进行下载。
- ![image-20200913132817207](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913132817207.png)
- 数据类型采用JSON格式，主要看[数据类型1(type == 1)格式说明]。

![image-20200913133226463](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913133226463.png)

- 了解完publish报文格式后，找到之前[接入OneNET平台]教程的程序，添加上上传数据点的功能即可。[点击下载源程序](https://github.com/TPYBoard/developmentBoard/tree/master/TPYBoard-v20x-master/TPYBoard v202 典型实例)

- 修改`mqtt.py`文件，如下：

  - ```python
    from simple import MQTTClient
    from machine import Pin
    import machine
    import micropython
    import json
    
    #选择G4引脚
    g4 = Pin(4, Pin.OUT, value=0)
    # MQTT服务器地址域名为：183.230.40.39,不变
    SERVER = "183.230.40.39"
    #设备ID
    CLIENT_ID = "628004536"
    #随便起个名字
    TOPIC = b"TurnipRobot"
    #产品ID
    username='371066'
    #产品APIKey:
    password='qljn7oMAVX=d7OrQ9SZyKW2=ruo='
    state = 0
    #要上报的数据点
    message = {'datastreams':[{
    'id':'temperature',
    'datapoints':[{'value':35}]}
    ]}
    
    def pubdata(data):
        j_d = json.dumps(data)
        j_l = len(j_d)
        arr = bytearray(j_l + 3)
        arr[0] = 1 #publish数据类型为json
        arr[1] = int(j_l / 256) # json数据长度 高位字节
        arr[2] = j_l % 256      # json数据长度 低位字节
        arr[3:] = j_d.encode('ascii') # json数据
        return arr
    
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
        elif msg == b"toggle":
            state = 1 - state
            g4.value(state)
    
    def main(server=SERVER):
        #端口号为：6002
        c = MQTTClient(CLIENT_ID, server,6002,username,password)
        c.set_callback(sub_cb)
        c.connect()
        c.subscribe(TOPIC)
        print("Connected to %s, subscribed to %s topic" % (server, TOPIC))
        #publish报文上传数据点
        c.publish('$dp',pubdata(message))
        print('publish message:',message)
    
        try:
            while 1:
                c.wait_msg()
        finally:
            c.disconnect()
    ```

- 程序解析

  - ```python
    def pubdata(data):
    j_d = json.dumps(data)
    j_l = len(j_d)
    arr = bytearray(j_l + 3)
    arr[0] = 1 #publish数据类型为json
    arr[1] = int(j_l / 256) # json数据长度 高位字节
    arr[2] = j_l % 256      # json数据长度 低位字节
    arr[3:] = j_d.encode('ascii') # json数据
    return arr
    ```

- 我们自定义一个pubdata方法，该方法的功能是组合成协议要求的报文格式。

  - ```python
    c.publish('$dp',pubdata(message))
    ```

- 设备使用`publish`报文来上传数据点。`$dp`为系统上传数据点的指令（2个字节的字符串）

- 成果展示：

  - ![image-20200913134613764](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913134613764.png)
  - 大家可根据上面学习到的内容进行扩展，比如接DHT11温湿度模块等各类传感器，上传温湿度、气压、光照等信息。 OneNET云平台除了支持MQTT协议外，还支持HTTP、TCP透传等多种协议，大家可以尝试添加其他协议的产品进行智能物联的开发。

