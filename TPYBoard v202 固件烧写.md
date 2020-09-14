# 18.TPYBoard v202 固件烧写

## 烧写固件

- 下载烧写固件所需的软件：在windows系统下可以使用ESPFlashDownloadTool_v3.3.4软件。不用担心不好找，见下面的附件压缩包。

  [flash_download_tools_v3.3.4_win.zip](http://www.tpyboard.com/ueditor/php/upload/file/20170222/1487749912530684.zip)

## 连接TPYBoard v202开发板

- 通过USB数据线将电脑和TPYBoard-esp8266开发板连接起来，会自动安装USB转串的驱动。安装完毕后，查看设备管理器，是否正确创建串口(我的电脑是COM44)

![image-20200913232358060](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913232358060.png)

- 打开`ESPFlashDownloadTool_v3.3.4`软件，根据下图进行设置。 选择`bin`格式的固件文件，固件可以去micropython官网下，[点击进入](http://micropython.org/download#esp8266)。 地址设置为`0x00000`，串口根据自己的实际情况选择，小编我的是`COM44`，波特率`115200`(必须设置为`115200`)。
- <img src="https://gitee.com/zr001/writeimges/raw/master/images/image-20200913232438306.png" alt="image-20200913232438306" style="zoom:67%;" />
- 设置完毕，点击`start`，提示上电同步。这时你需要让板子进入烧写模式。按住板子上的SW2(FLASH)按键不松，同时按一下SW1(RST)按键松开。
- 界面显示下载中... 同时右边区域显示设备的MAC地址，此时松手只需要等待下载完成即可。
- <img src="https://gitee.com/zr001/writeimges/raw/master/images/image-20200913232820970.png" alt="image-20200913232820970" style="zoom:67%;" />

