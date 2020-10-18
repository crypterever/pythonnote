# Python库-PIL库介绍

## PIL图像处理库中的基本概念介绍

### 通道（`bands`）

每张图片都是由一个或者多个数据通道构成。PIL允许在单张图片中合成相同维数和深度的多个通道。

以`RGB`图像为例，每张图片都是由三个数据通道构成，分别为`R`、`G`和`B`通道。而对于灰度图像，则只有一个通道。

对于一张图片的通道数量和名称，可以通过方法`getbands()`来获取。方法`getbands()`是`Image`模块的方法，它会返回一个字符串元组（`tuple`）。该元组将包括每一个通道的名称。

方法`getbands()`的使用如下：

```python
程序：from PIL import Image
	 im= Image.open('D:\\Code\\Python\\test\\img\\1.jpg')
	 im.getbands()

输出：('R', 'G', 'B')

程序：im_bands = im.getbands()
	 len(im_bands)

输出：3

程序：print im_bands[0]

输出：R

程序：print im_bands[1]

输出：G

程序：print im_bands[2]

输出：B
```

### 模式（`mode`）

图像的模式定义了图像的类型和像素的位宽。当前支持如下模式：

> getpixel(0,0)[`坐标`]

| 1     | 1位像素，表示黑和白，但是存储的时候每个像素存储为8bit,`模式“1”为二值图像，非黑即白。但是它每个像素用8个bit表示，0表示黑，255表示白。` |
| :---- | ------------------------------------------------------------ |
| L     | `1模式也是八位一个像素，只是值不是0就是255，非黑即白 L模式八位一个像素，值除了有0和255外，还有很多中间值表示灰色，所以称为灰度模式(L = R * 299/1000 + G * 587/1000+ B * 114/1000)` |
| P     | 8位像素，使用调色板映射到其他模式。                          |
| RGB   | 3x8位像素，为真彩色。                                        |
| RGBA  | 4x8位像素，有透明通道的真彩色。                              |
| CMYK  | 4x8位像素，颜色分离。模式“CMYK”为32位彩色图像，它的每个像素用32个bit表示。模式“CMYK”就是印刷四分色模式，它是彩色印刷时采用的一种套色模式，利用色料的三原色混色原理，加上黑色油墨，共计四种颜色混合叠加，形成所谓“全彩印刷”。<br />四种标准颜色是：C：Cyan = 青色，又称为‘天蓝色’或是‘湛蓝’M：Magenta = 品红色，又称为‘洋红色’；Y：Yellow = 黄色；K：Key Plate(blacK) = 定位套版色（黑色）。<br />C = 255 - R<br/>M = 255 - G<br/>Y = 255 - B<br/>K = 0 |
| YCbCr | 3x8位像素，彩色视频格式。模式“YCbCr”为24位彩色图像，它的每个像素用24个bit表示。YCbCr其中Y是指亮度分量，Cb指蓝色色度分量，而Cr指红色色度分量。人的肉眼对视频的Y分量更敏感，因此在通过对色度分量进行子采样来减少色度分量后，肉眼将察觉不到的图像质量的变化。<br />模式“RGB”转换为“YCbCr”的公式如下：<br />Cb：反映的是RGB输入信号蓝色部分与RGB信号亮度值之间的差异。<br/>Cr：反映了RGB输入信号红色部分与RGB信号亮度值之间的差异。<br /> |
| I     | 模式“`I`”为32位整型灰色图像，它的每个像素用32个bit表示，0表示黑，255表示白，(0,255)之间的数字表示不同的灰度。I = R * 299/1000 + G * 587/1000 + B * 114/1000<br />模式“I”与模式“L”的结果是完全一样，只是模式“L”的像素是8bit，而模式“I”的像素是32bit。 |
| F     | 32位浮点型像素。                                             |

`PIL`也支持一些特殊的模式，包括`RGBX`（有`padding`的真彩色）和`RGBa`（有自左乘`alpha`的真彩色）。

可以通过`mode`属性读取图像的模式。其返回值是包括上述模式的字符串。

属性`mode`的使用方法：

```python
程序：from PIL importImage
	 im =Image.open('D:\\Code\\Python\\test\\img\\1.jpg')
	 im.mode

输出：(800, 450)

程序：md = im.mode
	 print md

输出：RGB
```

### 尺寸（`size`）

通过`size`属性可以获取图片的尺寸。这是一个二元组，包含水平和垂直方向上的像素数。

属性`size`的使用方法：

```python
程序：from PIL importImage
	 im =Image.open('D:\\Code\\Python\\test\\img\\1.jpg')
	 im.size

输出：(800, 450)

程序：im_size = im.size
	 print im_size[0]

输出：800

程序：print im_size[1]

输出：450
```

### 坐标（`coordinate system`）

`PIL`使用笛卡尔像素坐标系统，坐标`(0，0)`位于左上角。注意：坐标值表示像素的角；位于坐标`（0，0）`处的像素的中心实际上位于`（0.5，0.5）`。

坐标经常用于二元组`（x，y）`。长方形则表示为四元组，前面是左上角坐标。例如，一个覆盖`800x600`的像素图像的长方形表示为`（0，0，800，600）`。

### 调色板（`palette`）

调色板模式 ("`P`")使用一个颜色调色板为每个像素定义具体的颜色值

### 信息（`info`）

使用`info`属性可以为一张图片添加一些辅助信息。这个是字典对象。加载和保存图像文件时，多少信息需要处理取决于文件格式。
```python
程序：from PIL import Image
	 im =Image.open('D:\\Code\\Python\\test\\img\\1.jpg')
	 print(im.info)

输出：{'jfif_version':(1, 1), 'jfif': 257, 'jfif_unit': 1, 'jfif_density': (96, 96), 'dpi': (96, 96)}

程序：im_info = im.info
	 print(im_info)

输出：{'jfif_version':(1, 1), 'jfif': 257, 'jfif_unit': 1, 'jfif_density': (96, 96), 'dpi': (96, 96)}

程序：print im_info['jfif_version']

输出：(1, 1)

程序：print im_info['jfif']

输出：257
```

### 滤波器（`filters`）

对于将多个输入像素映射为一个输出像素的几何操作，PIL提供了4个不同的采样滤波器：

`NEAREST`：最近滤波。从输入图像中选取最近的像素作为输出像素。它忽略了所有其他的像素。

`BILINEAR`：双线性滤波。在输入图像的2x2矩阵上进行线性插值。注意：PIL的当前版本，做下采样时该滤波器使用了固定输入模板。

`BICUBIC`：双立方滤波。在输入图像的4x4矩阵上进行立方插值。注意：PIL的当前版本，做下采样时该滤波器使用了固定输入模板。

`ANTIALIAS`：平滑滤波。这是PIL 1.1.3版本中新的滤波器。对所有可以影响输出像素的输入像素进行高质量的重采样滤波，以计算输出像素值。在当前的PIL版本中，这个滤波器只用于改变尺寸和缩略图方法。

注意：在当前的`PIL`版本中，`ANTIALIAS`滤波器是下采样（例如，将一个大的图像转换为小图）时唯一正确的滤波器。`BILIEAR`和`BICUBIC`滤波器使用固定的输入模板，用于固定比例的几何变换和上采样是最好的。

`Image`模块中的方法`resize()`和`thumbnail()`用到了滤波器。

方法`resize()`的使用如下：

方法`resize()`的定义为：

```python
resize(size, filter=None)=> image
```

```python
程序：from PIL import Image
	 im= Image.open('D:\\Code\\Python\\test\\img\\1.jpg')
	 print(im.size)

输出：(800, 450)

程序：im_resize = im.resize((256,256))
	 im_resize.size

输出：(256, 256)
```

对参数`filter`不赋值的话，方法`resize()`默认使用`NEAREST`滤波器。如果要使用其他滤波器可以通过下面的方法来实现：

```python
>>>im_resize0 = im.resize((256,256), Image.BILINEAR)

>>>im_resize0.size

(256, 256)

>>>im_resize1 = im.resize((256,256), Image.BICUBIC)

>>>im_resize1.size

(256, 256)

>>>im_resize2 = im.resize((256,256), Image.ANTIALIAS)

>>>im_resize2.size

(256, 256)

方法thumbnail ()的使用如下：

方法thumbnail ()的定义为：im.thumbnail(size, filter=None)

>>>from PIL import Image

>>> im= Image.open('D:\\Code\\Python\\test\\img\\1.jpg')

>>>im.size

(800, 450)

>>>im.thumbnail((200,200))

>>>im.size

(200,112)
```

这里需要说明的是，方法`thumbnail()`需要保持宽高比，对于`size=(200,200)`的输入参数，其最终的缩略图尺寸为`(200, 112)`。

对参数`filter`不赋值的话，方法`thumbnail()`默认使用`NEAREST`滤波器。如果要使用其他滤波器可以通过下面的方法来实现：

```python
>>> im= Image.open('D:\\Code\\Python\\test\\img\\1.jpg')

>>>im.size

(800, 450)

>>> im.thumbnail((200,200),Image.BILINEAR)

>>> im.size

(200, 112)

>>> im= Image.open('D:\\Code\\Python\\test\\img\\1.jpg')

>>>im.size

(800, 450)

>>> im.thumbnail((200,200), Image.BICUBIC)

>>> im.size

(200, 112)

>>> im= Image.open('D:\\Code\\Python\\test\\img\\1.jpg')

>>>im.size

(800, 450)

>>> im.thumbnail((200,200), Image.ANTIALIAS)

>>> im.size

(200, 112)
```



## Image模块

> 可以实现对图像的基本操作：open、save、conver、show...等功能。

### Image类中的函数

#### open

从文件加载图像，使用`open`函数，在`Image`模块：

```python
@winnerzr
	from PIL import Image  				# 调用库
    im = Image.open("demo.jpg")	   # 文件存在的路径 
    im.show()							 # 显示图片
```

> `Kite`Docs：[Image]().open
>
> function
>
> ## SIGNATURE
>
> ```python
> fp,
> mode=str
> ```
>
> ## RETURNS
>
> PngImageFile | JpegImageFile | GifImageFile
>
> ## HOW OTHERS USED THIS
>
> ```python
> open(fp)
> ```
>
> ## DESCRIPTION
>
> Opens and identifies the given image file.
>
> This is a lazy operation; this function identifies the file, but the file remains open and the actual image data is not read from the file until you try to process the data (or call the [:py:meth:`~PIL.Image.Image.load`](id1) method). See [:py:func:`~PIL.Image.new`](id3).
>
> | param fp:          | A filename (string), pathlib.Path object or a file object. The file object must implement[:py:meth:`~file.read`](id5),[:py:meth:`~file.seek`](id7), and[:py:meth:`~file.tell`](id9)methods, and be opened in binary mode. |
> | ------------------ | ------------------------------------------------------------ |
> | param mode:        | The mode. If given, this argument must be "r".               |
> | returns:           | An[:py:class:`~PIL.Image.Image`](id11)object.                |
> | exception IOError: |                                                              |
> |                    | If the file cannot be found, or the image cannot be opened and identified. |

#### new

给定一副尺寸和模式的图片，如果省略`color`参数，则创建的图片被黑色填充满，如果`color`参数是`None`值，则图片还没初始化。

使用给定的变量`mode`和`size`生成新的图像。`Size`是给定的宽/高二元组，这是按照像素数来计算的。对于单通道图像，变量`color`只给定一个值；对于多通道图像，变量`color`给定一个元组（每个通道对应一个值）。在版本`1.1.4`及其之后，用户也可以用颜色的名称，比如给变量`color`赋值为“`red`”。如果没有对变量`color`赋值，图像内容将会被全部赋值为`0`（为`黑色`）。如果变量`color`是空，图像将不会被初始化，即图像的内容全为`0`。这对向该图像复制或绘制某些内容是有用的。

```python
from PIL import Image
import matplotlib.pyplot as plt
img_b = Image.new("RGB",(32,32))#不指定color，则为黑色#000000
plt.imshow(img_b)
plt.show()
print(img_b.format)#python创建的图像，其格式为None
img_r = Image.new("RGB",(32,32),"red")
plt.imshow(img_r)
plt.show()
img_g = Image.new("RGB",(32,32),"#00FF00")
plt.imshow(img_g)
plt.show()
```

效果：![image-20201017204454586](https://gitee.com/zr001/writeimges/raw/master/img/image-20201017204454586.png)

![image-20201017204512481](https://gitee.com/zr001/writeimges/raw/master/img/image-20201017204512481.png)

![image-20201017204522225](https://gitee.com/zr001/writeimges/raw/master/img/image-20201017204522225.png)

> `Kite`Docs：[Image]().new
>
> function
>
> ## SIGNATURE
>
> ```python
> mode,
> size,
> color=0
> ```
>
> ## RETURNS
>
> Image
>
> ## HOW OTHERS USED THIS
>
> ```python
> new(mode, size, color)
> new(mode, size)
> new(mode, size, color)
> ```
>
> ## DESCRIPTION
>
> Creates a new image with the given mode and size.
>
> | param mode:  | The mode to use for the new image. See:concept-modes.        |
> | ------------ | ------------------------------------------------------------ |
> | param size:  | A 2-tuple, containing (width, height) in pixels.             |
> | param color: | What color to use for the image. Default is black. If given, this should be a single integer or floating point value for single-band modes, and a tuple for multi-band modes (one value per band). When creating RGB images, you can also use color strings as supported by the ImageColor module. If the color is None, the image is not initialised. |
> | returns:     | An[:py:class:`~PIL.Image.Image`](id1)object.                 |

#### blend

```python
Image.blend(image1,image2, alpha) ⇒ image
```

使用给定的两张图像及透明度变量`alpha`，插值出一张新的图像。这两张图像必须有一样的尺寸和模式。

> 合成公式为：`out = image1 (1.0 - alpha) + image2 alpha`

若变量`alpha`为`0.0`，返回第一张图像的拷贝。若变量`alpha`为`1.0`，将返回第二张图像的拷贝。对变量`alpha`的值无限制。

```python
from PIL import Image
im1 = Image.open("0000.jpg")
im2 = Image.open("00001.jpg")
print(im1.mode,im1.size)
print(im2.mode,im2.size)
im = Image.blend(im1, im2, 0.2)
im.show()
```

> `补充透明度获取方法`（包括更改`透明度`）：
>
> ```python
> from PIL import Image
> 
> img = Image.open("0000_switch.png")
> img = img.convert('RGBA') # 修改颜色通道为RGBA
> x, y = img.size # 获得长和宽
> 
> # # 设置每个像素点颜色的透明度
> for i in range(x):
>     for k in range(y):
>         color = img.getpixel((i, k))
>         color = color[:-1] + (0, )     # 将透明度设置为0
>         img.putpixel((i, k), color)
> 
> img.save("0000_switch.png") # 要保存为.PNG格式的图片才可以
> img2 = Image.open("0000_switch.png")
> img2.show()
> # color = img.getpixel((300,200)) 得到对应坐标的详细信息（R,G,B,alpha）
> # print(color)
> ```
>
> `输出`：![image-20201018161903307](https://gitee.com/zr001/writeimges/raw/master/img/image-20201018161903307.png)

#### merge

```python
Image.merge(mode,bands) ⇒ image
```

合并类使用一些单通道图像，创建一个新的图像。变量`bands`为一个图像的元组或者列表，每个通道的模式由变量`mode`描述。所有通道必须有相同的尺寸。
变量`mode`与变量`bands`的关系：

> `len(ImageMode.getmode(mode).bands)= len(bands)`

```python
from PIL import Image
im1 = Image.open("0000.jpg")
im2 = Image.open("0001.jpg")
r1,g1,b1 = im1.split()
r2,g2,b2 = im2.split()
print(r1.mode,r1.size,g1.mode,g1.size)
print(r2.mode,r2.size,g2.mode,g2.size)
new_im=[r1,g2,b2]
print(len(new_im))
im_merge = Image.merge("RGB",new_im)
im_merge.show()
```

![image-20201018163832803](https://gitee.com/zr001/writeimges/raw/master/img/image-20201018163832803.png)

![image-20201018163905692](https://gitee.com/zr001/writeimges/raw/master/img/image-20201018163905692.png)

### Image类中的方法

#### save

保存文件

```python
from PIL import Image
im = Image.open("demo.jpg")
print(im)							  # 打印出原图片的详细信息
im.save("demo.png")              # 将"0000.jpg"保存为"0000.png"
im = Image.open("demo.png")   	# 打开新的png图片
print(im.format, im.size, im.mode)  # 打印出转换后图片的相关信息（这里是格式，大小，色彩模式）
```



> `Kite`Docs：[Image]().save
>
> function
>
> ## SIGNATURE
>
> ```python
> fp,
> format=None,
> **params
> ```
>
> ## **PARAMS
>
> Expand
>
> ## HOW OTHERS USED THIS
>
> ```python
> save(fp)
> save(fp, format)
> save(fp, format, quality)
> save(fp, format)
> save(fp, quality)
> ```
>
> ## DESCRIPTION
>
> Saves this image under the given filename. If no format is specified, the format to use is determined from the filename extension, if possible.
>
> Keyword options can be used to provide additional instructions to the writer. If a writer doesn't recognise an option, it is silently ignored. The available options are described in the [:doc:`image format documentation <../handbook/image-file-formats>`](id1) for each writer.
>
> You can use a file object instead of a filename. In this case, you must always specify the format. The file object must implement the `seek`, `tell`, and `write` methods, and be opened in binary mode.
>
> | param fp:           | A filename (string), pathlib.Path object or file object.     |
> | ------------------- | ------------------------------------------------------------ |
> | param format:       | Optional format override. If omitted, the format to use is determined from the filename extension. If a file object was used instead of a filename, this parameter should always be used. |
> | param options:      | Extra parameters to the image writer.                        |
> | returns:            | None                                                         |
> | exception KeyError: |                                                              |
> |                     | If the output format could not be determined from the file name. Use the format option to solve this. |
> | exception IOError:  |                                                              |
> |                     | If the file could not be written. The file may have been created, and may contain partial data. |

#### mode

图像的模式：

```python
im.mode ==> string
```

图像的模式，常见的`mode`有“`L`”表示灰度图像，“`RGB`”表示真彩色图像，“`CMYK`”表示出版图像，表示图像所使用的像素格式，见

[^mode  ]:PIL基本概念

#### convert

产生不同格式的图片并输出：

```python
from PIL import Image
im = Image.open("0000.jpg") # 读取图片
new_im = im.convert('1')	# 输出格式为1的图片
print(new_im.mode)			 # 打印当前图像模式
new_im.show()				 # 显示转换之后的图片
```

![result](https://gitee.com/zr001/writeimges/raw/master/img/image-20201017214231901.png)

![demo](https://gitee.com/zr001/writeimges/raw/master/img/demo.png)

在数字图像处理中，针对不同的图像格式有其特定的处理算法。所以，在做图像处理之前，我们需要考虑清楚自己要基于哪种格式的图像进行算法设计及其实现。

对于`彩色图像`，不管其图像格式是PNG，还是BMP，或者JPG，在PIL中，使用Image模块的open()函数打开后，返回的图像对象的模式都是“`RGB`”。而对于`灰度图像`，不管其图像格式是PNG，还是BMP，或者JPG，打开后，其模式为“`L`”。



> `Kite`Docs：[Image]().convert
>
> function
>
> ## SIGNATURE
>
> ```python
> mode=None,
> matrix=None,
> dither=None,
> palette=0,
> colors=256
> ```
>
> ## RETURNS
>
> Image | JpegImageFile | PngImageFile | DibImageFile | Jpeg2KImageFile
>
> ## HOW OTHERS USED THIS
>
> ```python
> convert(mode)
> ```
>
> ## DESCRIPTION
>
> Returns a converted copy of this image. For the "P" mode, this method translates pixels through the palette. If mode is omitted, a mode is chosen so that all information in the image and the palette can be represented without a palette.
>
> The current version supports all possible conversions between "L", "RGB" and "CMYK." The **matrix** argument only supports "L" and "RGB".
>
> When translating a color image to black and white (mode "L"), the library uses the ITU-R 601-2 luma transform:
>
> ```python
> L = R * 299/1000 + G * 587/1000 + B * 114/1000
> ```
>
> The default method of converting a greyscale ("L") or "RGB" image into a bilevel (mode "1") image uses Floyd-Steinberg dither to approximate the original image luminosity levels. If dither is NONE, all non-zero values are set to 255 (white). To use other thresholds, use the [:py:meth:`~PIL.Image.Image.point`](id1) method.
>
> | param mode:    | The requested mode. See:concept-modes.                       |
> | -------------- | ------------------------------------------------------------ |
> | param matrix:  | An optional conversion matrix. If given, this should be 4- or 12-tuple containing floating point values. |
> | param dither:  | Dithering method, used when converting from mode "RGB" to "P" or from "RGB" or "L" to "1". Available methods are NONE or FLOYDSTEINBERG (default). |
> | param palette: | Palette to use when converting from mode "RGB" to "P". Available palettes are WEB or ADAPTIVE. |
> | param colors:  | Number of colors to use for the ADAPTIVE palette. Defaults to 256. |
> | rtype:         | [:py:class:`~PIL.Image.Image`](id3)                          |
> | returns:       | An[:py:class:`~PIL.Image.Image`](id5)object.                 |

#### format

```python
im.format==> string or none
```

这个属性可以识别图像来源，如果图像不是从文件读取它的值就是`None`。

```python
from PIL import Image
im = Image.open("0000.jpg")
print(im.format)           # 打印出格式信息
im.show()
```

输出：

![image-20201018104928809](https://gitee.com/zr001/writeimges/raw/master/img/image-20201018104928809.png)

#### size

```python
im.size ==> (width, height)
```

图像的尺寸，按照像素数计算，它的返回值为宽度和高度的二元组（`width`，`height`）

```python
from PIL import Image
im = Image.open("0000.jpg")
print(im.size)				# 打印出尺寸信息
im.show()
```

#### palette

```python
im.palette ==> palette or None
```

颜色调色板表格。如果图像的模式是“P”，则返回ImagePalette类的实例；否则，将为None。

```python
from PIL import Image
im = Image.open(".jpg")
print(im.palette) 
```

输出：![image-20201018110130581](https://gitee.com/zr001/writeimges/raw/master/img/image-20201018110130581.png)

> 对图像进行`convert`之后：
>
> ```python
> from PIL import Image
> im = Image.open("0000.jpg")
> print(im.palette) 
> new_im = im.convert('P')
> print(new_im.mode)
> print(new_im.palette)
> ```
>
> 输出：![image-20201018110353455](https://gitee.com/zr001/writeimges/raw/master/img/image-20201018110353455.png)

#### info

```python
im.info ==》dictionary
```

存储图像相关数据的字典。文件句柄使用该字典传递从文件中读取的各种非图像信息。大多数方法在返回新的图像时都会忽略这个字典；因为字典中的键并非标准化的，对于一个方法，它不能知道自己的操作如何影响这个字典。如果用户需要这些信息，需要在方法`open()`返回时保存这个字典。

```python
from PIL import Image
im = Image.open("0000.jpg")
print(im.info)
```

#### copy

```python
im.copy() ==>image
```

拷贝这个图像。如果用户想粘贴一些数据到这张图，可以使用这个方法，但是原始图像不会受到影响。

```python
from PIL import Image
im = Image.open("0000.jpg")
im_copy = im.copy() 
```



#### corp

```python
im.corp(box) ==> image
```

从当前的图像中返回一个矩形区域的拷贝。变量`box`是一个四元组，定义了左、上、右和下的像素坐标。用来表示在原始图像中截取的位置坐标，如`box(100,100,200,200)`就表示在原始图像中以左上角为坐标原点，截取一个`100*100`（像素为单位）的图像，为方便理解，如下为示意图`box（b1,a1,b2,a2）`。作图软件为`Visio2016`。这是一个懒操作。对源图像的改变可能或者可能不体现在裁减下来的图像中。为了获取一个分离的拷贝，对裁剪的拷贝调用方法`load()`。

![image-20201018153138526](https://gitee.com/zr001/writeimges/raw/master/img/image-20201018153138526.png)

```python
from PIL import Image
im = Image.open("0000.jpg")
box = (300, 100, 700, 700)              ##确定拷贝区域大小
region = im.crop(box)                   ##将im表示的图片对象拷贝到region中，大小为box
region.show()
```

#### paste

```python
im.paste(image,box)
```

将一张图粘贴到另一张图像上。变量`box`或者是一个给定左上角的2元组，或者是定义了左，上，右和下像素坐标的4元组，或者为空（与`（0，0）`一样）。如果给定`4`元组，被粘贴的图像的尺寸必须与区域尺寸一样。如果模式不匹配，被粘贴的图像将被转换为当前图像的模式。

```python
from PIL import Image
im = Image.open("0000.jpg")
box=[0,0,100,100]
im_crop = im.crop(box)
print(im_crop.size,im_crop.mode)
im.paste(im_crop, (100,100))             ##(100,100,0,0)
im.paste(im_crop, (400,400,500,500))
im.show()
```

#### filter

```python
im.filter(filter) ==> image
```

返回一个使用给定滤波器处理过的图像的拷贝。具体参考图像滤波在`ImageFilter` 模块的应用，在该模块中，预先定义了很多增强滤波器，可以通过`filter()` 函数使用，预定义滤波器包括：`BLUR`、`CONTOUR`、`DETAIL`、`EDGE_ENHANCE`、`EDGE_ENHANCE_MORE`、`EMBOSS`、`FIND_EDGES`、`SMOOTH`、`SMOOTH_MORE`、`SHARPEN`。其中`BLUR`就是均值滤波，`CONTOUR`找轮廓，`FIND_EDGES`边缘检测，使用该模块时，需先导入。

```python
from PIL import Image
from PIL import ImageFilter                         ## 调取ImageFilter
imgF = Image.open("0000.jpg")
bluF = imgF.filter(ImageFilter.BLUR)                ##均值滤波
conF = imgF.filter(ImageFilter.CONTOUR)             ##找轮廓
edgeF = imgF.filter(ImageFilter.FIND_EDGES)         ##边缘检测
imgF.show()
bluF.show()
conF.show()
edgeF.show()
```

#### split

```python
im.split() ⇒ sequence
```

返回当前图像各个通道组成的一个元组。例如，分离一个“`RGB`”图像将产生三个新的图像，分别对应原始图像的每个通道（红，绿，蓝）。

```python
from PIL import Image
im = Image.open("0000.jpg")
r,g,b = im.split()
print(r.mode)
print(r.size)
print(im.size)
r.show()
# g.show()
# b.show()
```

![image-20201018162629568](https://gitee.com/zr001/writeimges/raw/master/img/image-20201018162629568.png)

#### rotate

```python
im.rotate(angle) ⇒ image
im.rotate(angle,filter=NEAREST, expand=0) ⇒ image
```

返回一个按照给定角度顺时钟围绕图像中心旋转后的图像拷贝。变量`filter`是`NEAREST`、`BILINEAR`或者`BICUBIC`之一。如果省略该变量，或者图像模式为“`1`”或者“`P`”，则默认为`NEAREST`。变量`expand`，如果为`true`，表示输出图像足够大，可以装载旋转后的图像。如果为`false`或者`缺省`，则输出图像与输入图像尺寸一样大。

```python
from PIL import Image
im = Image.open("0000.jpg")
im_45 = im.rotate(45)
im_30 = im.rotate(30, Image.NEAREST,1)
print(im_45.size,im_30.size)
im_45.show()
im_30.show()
```

#### seek

```python
im.seek(frame)
```

在给定的文件序列中查找指定的帧。如果查找超越了序列的末尾，则产生一个`EOFError`异常。当文件序列被打开时，`PIL`库自动指定到`第0帧`上。

```python
from PIL import Image
im_gif = Image.open("0000.gif")
print(im_gif.mode)
im_gif.show()    ##第0帧
im_gif.seek(3)
im_gif.show()
im_gif.seek(9)
im_gif.show()
```

![image-20201018164739066](https://gitee.com/zr001/writeimges/raw/master/img/image-20201018164739066.png)