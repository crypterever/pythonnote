# 2. TPYBoard v202简介

  TPYBoard v202是遵照MIT协议，以MicroPython为基础，研发的一款支持Python和lua语言的Wifi通信开发板，TPYBoard v202有9个通用GPIO口，1费ADC接口，1个SPI接口，1个I2C 接口，1个USART接口。

##   通用方法 `machine`类库：

  ```python
  import machine
  machine.freq()          # 获取CPU的频率
  machine.freq(160000000) # 设置CPU频率为 160 MHz
  ```

  `esp`类库：

  ```python
  import esp
  esp.osdebug(None)       # 关闭供应商O/S调试消息
  esp.osdebug(0)          # 将供应商O/S调试消息重定向到UART（0）
  ```

##   联网 `network`类库：

> `AP`模式: `Access Point`，提供无线接入服务，允许其它无线设备接入，提供数据访问，一般的无线路由/网桥工作在该模式下。`AP`和`AP`之间允许相互连接
>
> `STA`模式: `Station`, 类似于无线终端，`STA`本身并不接受无线的接入，它可以连接到AP，一般无线网卡即工作在该模式。
>
> 简单地说，AP模式指的是可以将板子当作路由器来使用，STA模式指的是将板子连接到wifi上网

  ```python
  import network
  wlan = network.WLAN(network.STA_IF) # 将v202设置成STA模式
  wlan.active(True)       # 激活接口
  wlan.scan()             # 扫描当前可用WiFi
  wlan.isconnected()      # 检查工作站是否连接到AP
  wlan.connect('essid', 'password') # 连接WiFi名称，WiFi密码
  wlan.config('mac')      # 得到接口对应的mac地址
  wlan.ifconfig()         # 得到接口的IP地址、网络掩码、网关、DNS地址
  ap = network.WLAN(network.AP_IF) # 创建可用接口
  ap.active(True)         # 激活接口
  ap.config(essid='ESP-AP') # 设置开发板的WiFi名称
  ```

##   连接到本地`WiFi`网络：

  ```python
  def do_connect():
          import network
          wlan = network.WLAN(network.STA_IF)
          wlan.active(True)
          if not wlan.isconnected():
                  print('connecting to network...')
                  wlan.connect('essid', 'password') # 连接WiFi名称，WiFi密码 
                  while not wlan.isconnected():
                          pass
          print('network config:', wlan.ifconfig())
  ```

##   延迟和时间 `time` 类库

  ```python
  import time
  time.sleep(1)           # 延时一秒
  time.sleep_ms(500)      # 延时500毫秒
  time.sleep_us(10)       # 延时10微秒
  start = time.ticks_ms() # 获取毫秒计数器
  delta = time.ticks_diff(time.ticks_ms(), start) # 计算时间差，精确到毫秒级
  ```

##   计时器

  ```python
  import time
  time.sleep(1)           # sleep for 1 second
  time.sleep_ms(500)      # sleep for 500 milliseconds
  time.sleep_us(10)       # sleep for 10 microseconds
  start = time.ticks_ms() # get millisecond counter
  delta = time.ticks_diff(time.ticks_ms(), start) # compute time difference
  
  周期以毫秒为单位。
  ```

##   引脚和`GPIO` 使用`machine.Pin`类库：

  ```python
  from machine import Pin
  p0 = Pin(0, Pin.OUT)    # 将GPIO0设置为输出模式
  p0.high()               # 设置引脚为高电位
  p0.low()                # 设置引脚为低电位
  p0.value(1)             
  p2 = Pin(2, Pin.IN)     # 将GPIO2设置为输入模式
  print(p2.value())       # 得到引脚对应的高低电平信息
  p4 = Pin(4, Pin.IN, Pin.PULL_UP) # e启动内部上拉电阻
 led = Pin(2, Pin.OUT)
 led.on() # 熄灭灯
 led.off() # 点亮灯
 led.value(1) # 熄灭灯
 led.value(0) # 点亮灯
              # 即低电平有效，高电平无效
  ```

  可用引脚为：0,1,2,3,4,5,12,13,14,15,16，其对应于`ESP8266`芯片的实际`GPIO`引脚号。请注意，许多终端用户板使用自己的adhoc引脚编号（标记为D0，D1，...）。由于`MicroPython`支持不同的单板和模块，所以选择物理引脚编号作为最低的公分母。对于逻辑引脚和物理芯片引脚之间的映射，请参阅电路板文档。

  注意，引脚（1）和引脚（3）分别是REPL UART TX和RX。还要注意，Pin（16）是一个特殊的引脚（用于从深睡眠模式唤醒），可能不适用于更高级别的类 Neopixel。

  PWM（脉宽调制） 除引脚（16）外的所有引脚都可以使能PWM。所有通道都有一个`频率`，范围介于`1到1000`（以`Hz`为单位）。`占空比`介于`0和1023`之间。`duty`属于`[0，1023]`

##   使用machine.PWM类：

  ```python
  from machine import Pin, PWM
  pwm0 = PWM(Pin(0))      # 从当前引脚创建PWM对象
  pwm0.freq()             # 获取当前频率
  pwm0.freq(1000)         # 设置频率
  pwm0.duty()             # 获取当前占空比
  pwm0.duty(200)          # 设置占空比
  pwm0.deinit()           # 关闭引脚的PWM功能
  pwm2 = PWM(Pin(2), freq=500, duty=512) # create and configure in one go
  ```

  ADC（模数转换） ADC在专用引脚上可用。请注意，ADC引脚上的输入电压必须在0v和1.0v之间。read()返回的值属于0（0.0伏）到1024（1.0伏）。注意输入最大只能为1伏电压，当你想要测量更大的电压时必须使用分压电路（voltage divider circuit）。

##   使用machine.ADC类：

  ```python
  from machine import ADC
  adc = ADC(0)            # create ADC object on ADC pin
  adc.read()              # read value, 0-1024
  ```

## SPI总线 有两个SPI驱动程序。

一个在软件（bit-banging）中实现，并可在所有引脚上工作：

  ```python
  from machine import Pin, SPI
  # construct an SPI bus on the given pins# polarity is the idle state of SCK# phase=0 means sample on the first edge of SCK, phase=1 means the second
  spi = SPI(-1, baudrate=100000, polarity=1, phase=0, sck=Pin(0), mosi=Pin(2), miso=Pin(4))
  spi.init(baudrate=200000) # set the baudrate
  spi.read(10)            # read 10 bytes on MISO
  spi.read(10, 0xff)      # read 10 bytes while outputing 0xff on MOSI
  buf = bytearray(50)     # create a buffer
  spi.readinto(buf)       # read into the given buffer (reads 50 bytes in this case)spi.readinto(buf, 0xff) # read into the given buffer and output 0xff on MOSI
  spi.write(b'12345')     # write 5 bytes on MOSI
  buf = bytearray(4)      # create a buffer
  spi.write_readinto(b'1234', buf) # write to MOSI and read from MISO into the buffer
  spi.write_readinto(buf, buf) # write buf to MOSI and read MISO back into buf
  ```

  硬件SPI更快（高达80Mhz），但仅适用于以下引脚： MISO	is	GPIO12， MOSI 	is	GPIO13，SCK	is	GPIO14。它具有与上述bitbanging SPI类相同的方法，除了构造函数和init的引脚参数（正如固定的那样）：

  ```python
  from machine import Pin, SPI
  hspi = SPI(1, baudrate=80000000, polarity=0, phase=0) # 设置波特率
  ```

  I2C总线 I2C驱动程序通过以下程序来实现，并可在TPYBoard v202所有引脚上工作：

  ```python
  from machine import Pin, I2C  # construct an I2C bus
  i2c = I2C(scl=Pin(5), sda=Pin(4), freq=100000)
  i2c.readfrom(0x3a, 4)   # read 4 bytes from slave device with address 0x3a
  i2c.writeto(0x3a, '12') # write '12' to slave device with address 0x3a
  buf = bytearray(10)     # create a buffer with 10 bytes
  i2c.writeto(0x3a, buf)  # write the given buffer to the slave
  ```

##  深度睡眠模式 

将`GPIO16`连接到复位引脚（`RST`）。可以使用以下代码进行睡眠，唤醒并检查复位原因：

从深睡眠中唤醒后，所有之前的记忆都被抹除，不过会`boot.py`一如既往地执行，你可以编写代码使得在被唤醒后做一些事情。比如打印唤醒的模式，使用以下代码：

  ```python
  import machine
  # configure RTC.ALARM0 to be able to wake the device
  rtc = machine.RTC()rtc.irq(trigger=rtc.ALARM0, wake=machine.DEEPSLEEP)
  # check if the device woke from a deep sleepif machine.reset_cause() == machine.DEEPSLEEP_RESET:
          print('woke from a deep sleep')
  # set RTC.ALARM0 to fire after 10 seconds (waking the device)
  rtc.alarm(rtc.ALARM0, 10000)
  # put the device to sleep
  machine.deepsleep()
  ```

  `OneWire`驱动 `OneWire`驱动程序通过以下程序实现，并可在`TPYBoard v202`所有引脚上工作：

  ```python
  from machine import Pinimport onewire
  ow = onewire.OneWire(Pin(12)) # create a OneWire bus on GPIO12
  ow.scan()               # return a list of devices on the bus
  ow.reset()              # reset the bus
  ow.readbyte()           # read a byte
  ow.writebyte(0x12)      # write a byte on the bus
  ow.write('123')         # write bytes on the bus
  ow.select_rom(b'12345678') # select a specific device by its ROM code
  ```

##   DS18S20和DS18B20的驱动程序：

  ```python
  import time, ds18x20
  ds = ds18x20.DS18X20(ow)
  roms = ds.scan()
  ds.convert_temp()
  time.sleep_ms(750)
  for rom in roms:
          print(ds.read_temp(rom))
  ```

  确保在数据线上放置4.7k的上拉电阻。请注意，convert_temp()每次要采样温度时都必须调用该方法。

##   NeoPixel驱动 使用neopixel类库：

  ```python
  from machine import Pin
  from neopixel import NeoPixel
  pin = Pin(0, Pin.OUT)   # set GPIO0 to output to drive NeoPixels
  np = NeoPixel(pin, 8)   # create NeoPixel driver on GPIO0 for 8 pixels
  np[0] = (255, 255, 255) # set the first pixel to white
  np.write()              # write data to all pixels
  r, g, b = np[0]         # get first pixel colour
  ```

##   对于NeoPixel的入门使用：

  ```python
  import esp
  esp.neopixel_write(pin, grb_buf, is800khz)
  ```

##   APA102驱动

 使用apa102类库：

  ```python
  from machine import Pin
  from apa102 import APA102
  clock = Pin(14, Pin.OUT)     # set GPIO14 to output to drive the clock
  data = Pin(13, Pin.OUT)      # set GPIO13 to output to drive the data
  apa = APA102(clock, data, 8) # create APA102 driver on the clock and the data pin for 8 pixels
  apa[0] = (255, 255, 255, 31) # set the first pixel to white with a maximum brightness of 31apa.write()                  # write data to all pixels
  r, g, b, brightness = apa[0] # get first pixel colour
  ```

  对于APA102的入门使用：

  ```python
  import esp
  esp.apa102_write(clock_pin, data_pin, rgbi_buf)
  ```

  DHT驱动 DHT驱动程序通过以下代码实现，并可在TPYBoard v202所有引脚上工作：

  ```python
  import dhtimport machine
  d = dht.DHT11(machine.Pin(4))
  d.measure()d.temperature() # eg. 23 (째C)
  d.humidity()    # eg. 41 (% RH)
  d = dht.DHT22(machine.Pin(4))
  d.measure()d.temperature() # eg. 23.6 (째C)
  d.humidity()    # eg. 41.3 (% RH)
  ```

# 