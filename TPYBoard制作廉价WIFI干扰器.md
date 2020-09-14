# 14.TPYBoard v202 邪恶改装：TPYBoard制作廉价WIFI干扰器

> `esp8266`可以实现简单的干扰功能，包括`断网`、`复制`、`欺骗`等等

## 搭建开发环境：

- 使用`esp8266`制作的`Deauth`无限攻击的开源固件，使用`arduino`开发的
- [地址](https://github.com/PakchoiFood/ESP8266_deauther)

- 里面包含了arduino IDE（arduino-1.8.2-windows.exe）和固件源码（esp8266_deauther-master.rar）。另外，还需要esp8266开发包（Arduino15.rar）可以从下面链接：http://pan.baidu.com/s/1bpnJMkn 下载。

## 配置步骤

- 下载之后解压：![image-20200913150914270](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913150914270.png)

- 双击安装`arduino`
- 安装完毕之后，打开首选项，点击红色区域进入`SDK`目录![image-20200913151245252](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913151245252.png)

- 我的路径是：C:\Users\Administrator\AppData\Local\Arduino15

- 将从网盘下载的Arduino15.rar 解压，把里面全部的文件直接覆盖`C:\Users\Administrator\AppData\Local\Arduino15`下文件。
- ![image-20200913152202750](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913152202750.png)

## 硬件器件的准备

将`tpyboard V202`与电脑连接，找到arduino IDE菜单里工具—》开发板 在右侧出来的菜单中向下找，会找到一个`TPYBoard v202`点击选中。

![image-20200913152446954](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913152446954.png)

## 编译烧写固件

- 解压esp8266_deauther-master.rar，arduino IDE菜单栏 文件-》打开esp8266_deauther-master源码包esp8266_deauther\esp8266_deauther.ino
- TPYBoard v202 使用micro USB数据线接入电脑。查看安装的usb转串的端口。打开电脑的设备管理器（这里是COM11）

![image-20200913152652580](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913152652580.png)

- 工具-》端口，选择COM4（根据自己的实际端口号选择）

  ![image-20200913152739642](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913152739642.png)

- 菜单栏下面的绿色图标菜单区，选择上传，开始编译，烧写固件

![image-20200913152822888](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913152822888.png)

- 等待编译完成，出现下图信息（状态：变为“上传”）时，按住FLASH的同时，按一下RST按键并松开，让TPYBoard v202复位一下，进入烧写模式。继续按着FLASH,出现下面的信息时就可以松开FLASH按键了。

![image-20200913152917742](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913152917742.png)

- 烧写固件时，板子上的蓝色小灯会一直快速闪烁。![image-20200913153009793](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913153009793.png)

- 烧写完毕后，显示上传成功，板子上的蓝色小LED会停止闪烁。![image-20200913153059361](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913153059361.png)

## 测试攻击效果

- 成功烧写固件后，打开无线会搜索到名称为TPYBoard v202 的热点，密码默认tpyboard，进行连接。

![image-20200913154709197](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913154709197.png)

- 连接成功后，打开浏览器输入192.168.4.1 。点击[我已阅读并理解上面的通知]（本次实验只用于测试实验，请谨慎使用）。
- 网页原版是英文的，为了方便使用，我简单的翻译了一下（wifi SSID和密码也做了修改），下载的压缩包里也有英文原版的。

![image-20200913154750093](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913154750093.png)

- 点击进来以后，首先扫描一下附近的wifi。点击[扫描]。

  ![image-20200913154809645](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913154809645.png)

- 接下来我们选择一个wifi做一下攻击的测试，为了方便测试是否成功，选择平时经常使用的wifi，我的列表中选择boda。![image-20200913154837175](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913154837175.png)

- 选择好后，点击最上方菜单栏[攻击]，进入攻击页面。

![image-20200913154856972](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913154856972.png)

- 攻击方式有3种，Deauther、Beacon和Probe-Request。页面最下方有对这3种方式的介绍，Probe-Request实在不知道怎么翻译，大神们可以指点一下。

![image-20200913154927658](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913154927658.png)

- 我们这次使用Deauther方式，阻止客户端连接，点击[START]开始攻击。

![image-20200913154948933](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913154948933.png)

- 找一个手机做一下实验，看是否还能连上boda。

![image-20200913155017067](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913155017067.png)

> 如果是第一次连接的话，会一直停在正在连接的界面上，无法连接成功。
> 如果原本连接着，会被强迫断线。点击[STOP],停止攻击。停止后，手机成功连接上boda了。
>
> ![image-20200913155155865](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913155155865.png)
>
> `esp8266_deauther`里面还带了`wifi`复制等其他攻击方式，大家可以自己尝试一下。

![image-20200913161858438](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913161858438.png)

![image-20200913161910834](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913161910834.png)

