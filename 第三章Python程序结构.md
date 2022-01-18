# 第三章Python程序结构

> ![image-20200916201711562](https://gitee.com/zr001/writeimges/raw/master/images/image-20200916201711562.png)

## 3.1print函数

- 单行程序输出
  
- ![image-20200916201938547](https://gitee.com/zr001/writeimges/raw/master/images/image-20200916201938547.png)
  
- 多行程序输出
  
- ![image-20200916202029811](https://gitee.com/zr001/writeimges/raw/master/images/image-20200916202029811.png)
  
- 给`print`函数提供一个参数列表

  - ![image-20200916202139623](https://gitee.com/zr001/writeimges/raw/master/images/image-20200916202139623.png)

  - > python 自动在显示的每一项之间添加空格

## 3.2使用Python库

### 3.2.1random库

> ![image-20200916202741780](C:\Users\winnerzr\AppData\Roaming\Typora\typora-user-images\image-20200916202741780.png)

`random`库包含大量函数，下面的是`randint`函数

> ![image-20200916203145176](https://gitee.com/zr001/writeimges/raw/master/images/image-20200916203145176.png)返回介于`1`到`6`之间的随机数
>
> ![image-20200916203308739](https://gitee.com/zr001/writeimges/raw/master/images/image-20200916203308739.png)

### 3.2.2time库

### 3.2.3sleep函数

我在程序中使用`sleep`函数，留给用户读取程序显示的内容，可以用在`即点即用`的程序中，推迟程序的结束时间，让用户看清程序运行过程。

```python
import time
print('I will need to think about that..')
time.sleep(5)
print('The answer is:42')
```

> ![image-20200916204040179](https://gitee.com/zr001/writeimges/raw/master/images/image-20200916204040179.png)

## 3.3Python注释

> 在`IDLE`中注释显示为红色![image-20200916204804164](https://gitee.com/zr001/writeimges/raw/master/images/image-20200916204804164.png)

## 3.5添加一些snaps函数

### 3.5.1添加`pygame`库

> ```python
> py -m pip install pygame --user
> ```

### 3.5.2snaps函数

- 1.显示文本

  - `snaps`函数`display_message`的参数是一个文本字符串，该函数在显示器窗口中显示相应的字符串，

  - ```python
    import snaps
    snaps.display_meassage('This is smaller text i green on the top left',color=(0,255,0),size=50,horiz='left',vert='top') # 颜色，文本大小，文字对齐（屏幕左侧，右侧，中心对齐），文本对齐（屏幕顶部，底部，中心对齐）
    ```

    

- 2.显示图像

  - ```python
    import snaps
    snaps.display_image('Housemartins.jpg') # 图像文件名，与程序文件一起，jpg或png
    snaps.display_meassage('HullRocks',color(255,255,255),size=50,vert='top')# 颜色，文本大小，文字对齐（屏幕左侧，右侧，中心对齐），文本对齐（屏幕顶部，底部，中心对齐）
    ```

    ![1600264400008](https://gitee.com/zr001/writeimges/raw/master/images/1600264400008.jpg)

- 3.播放音频

  - ```python
    import snaps
    snaps.play_sound('ding.wav')
    ```

    

