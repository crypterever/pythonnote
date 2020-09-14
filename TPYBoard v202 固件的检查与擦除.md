# 17.TPYBoard v202 固件的检查与擦除

## 准备工作

- TPYBoard v202板子 1块
- micro USB数据线 1条
- 电脑 1台（本次实验以win7为例）
- PuTTY(工具)

## 所需器件

- TPYBoard v202开发板 1块
- USB数据线（MicroUSB） 1条
- L298N电机驱动模块 1个
- 小车套件包（底板、电机等） 1个
- 18650电池 2节
- 18650电池盒 1个

## 固件完整性检查

- 安装`putty`

- 通过USB数据线将电脑和TPYBoard v202开发板连接起来，会自动安装USB转串的驱动。安装完毕后，查看设备管理器，是否正确创建串口。![image-20200913231149152](https://gitee.com/zr001/writeimges/raw/master/images/image-20200913231149152.png)

- 打开PuTTY，根据下图标记的红色框进行设置。<img src="https://gitee.com/zr001/writeimges/raw/master/images/image-20200913231207789.png" alt="image-20200913231207789" style="zoom:150%;" />

- 设置完成后，单击open按钮<img src="https://gitee.com/zr001/writeimges/raw/master/images/image-20200913231240979.png" alt="image-20200913231240979" style="zoom:150%;" />

- 按下板子上的rst，进行重置<img src="https://gitee.com/zr001/writeimges/raw/master/images/image-20200913231258691.png" style="zoom:150%;" />

- 按下图命令操作

  ```python
  import esp
  esp.check_fw()
  ```

  <img src="https://gitee.com/zr001/writeimges/raw/master/images/image-20200913231437386.png" alt="image-20200913231437386" style="zoom:150%;" />

  > 如果最后显示`True`，代表固件是完整的，否则可能存在问题。如果显示False，最好重新刷一次固件。 详情可参考下一篇文档进行固件的烧写。

## 固件的擦除

- 安装`Python`环境

- 安装`esptool`和`pyserial`，在CMD命令行里运行：

  ```python
  pip install esptool
  ```

  和

  ```python
  pip install pyserial
  ```

- 擦除flash

- 打开`cmd`，运行指令：

  ```python
  esptool.py --port COM3 erase_flash
  ```

> **注意：**
>
> 执行擦除的指令前，需要像烧录固件一样，让esp8266进入`烧写模式`)即`按住`板上的`FLASH`键不放，`按下RST`键`松开`，当界面显示出MAC地址后，即可`松开FLASH`按键等待擦除完毕。如果在超时时间内没有让板子进入烧写模式的话 ，就会出现如下的错误提示：`A fatal error occurred: Failed to connect to ESP8226`
>
> 固件成功擦除后，可参考下一篇文档进行固件的烧写。

