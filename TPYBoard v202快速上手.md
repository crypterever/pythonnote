# 1. TPYBoard v202快速上手

> ![image-20200911194359125](https://gitee.com/zr001/writeimges/raw/master/images/image-20200911194359125.png)
>
> ![image-20200911194433114](https://gitee.com/zr001/writeimges/raw/master/images/image-20200911194433114.png)

- 打开对应端口
- 将`main.py`加载到`Tpyboard`
- 运行完下面的程序，可以搜索到名为“TPYBoard v202”的WIFI，并可以成功连接。

```python
import network

# 将v202设置成AP模式
ap_if = network.WLAN(network.AP_IF)
# 激活接口
ap_if.active(True)
# 开放WIFI。名称:TPYBoard v202 密码:12345678
ap_if.config(essid='TPYBoard v202',password='12345678')
```

# 