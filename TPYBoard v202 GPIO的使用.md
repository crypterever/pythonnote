# 3.TPYBoard v202 GPIO的使用

## 3.1GPIO的介绍

> `GPIO`（General Purpose I/O Ports）意思为通用输入/输出端口，通俗地说，就是一些引脚，可以通过它们输出高低电平或者通过它们读入引脚的状态-是高电平或是低电平。

![GPIO](https://gitee.com/zr001/writeimges/raw/master/images/image-20200911204659059.png)

- 通过上图大家可以看到开发板上的`ESP8266`模块上有一个蓝色的LED灯，它与板子的`G2`引脚相连。当控制G2输出低电平时，LED点亮，反之熄灭。开发板上有两个按键，`RST`按键和`FLASH`按键。

- `RST`按键：复位按键，用于开发板的硬复位

- `FLASH`按键：FLASH按键，主要与RST按键搭配使用，使开发板进入烧录模式，与`G0`引脚相连

  > `TPYBoard v202`开发板支持`MicroPython`开发，同时也只支持`Lua`语言开发。为了方便大家使用，下表列举了TPYBoard v202开发板上的引脚编号与NodeMCU、MicroPython之间的对应关系。![image-20200911205000226](https://gitee.com/zr001/writeimges/raw/master/images/image-20200911205000226.png)
  >
  > 可用于`GPIO`操作的引脚有：`G0`,`G2`,`G4`,`G5`,`G12`,`G13`,`G14`,`G15`,`G16`，其中`G16`是一个特殊的引脚，用于从深度睡眠模式唤醒模块。还需要注意一点，开发板上只有一个串口，将其引出为USB虚拟串口用于`REPL`操作，当你需要使用串口时，应注意避免冲突。
  >
  > `实现功能`：运行新程序后，你会看到板载的蓝色LED灯会每隔3秒亮灭一次，并一直循环下去。
  >
  > ```python
  > from machine import Pin
  > import time
  > 
  > p2 = Pin(2, Pin.OUT)    # 创建一个引脚对象p2，使用GPIO2（G2）引脚，输出模式
  > p2.value(1)             # 设置引脚输出高电平，即板载蓝色LED熄灭
  > 
  > while True:
  > p2.value(0)           # 设置引脚输出低电平，即板载蓝色LED点亮
  > print(p2.value())     # 读取引脚的电平值，并打印
  > time.sleep(3)         # 延时3秒
  > p2.value(1)
  > print(p2.value())
  > time.sleep(3)
  > ```

