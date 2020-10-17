# Python库-PIL库介绍

## Image模块

> 可以实现对图像的基本操作：open、save、conver、show...等功能。

### Image类中的函数

#### open

从文件加载图像，使用`open`函数，在`Image`模块：

```python
@winnerzr
	from PIL import Image  				# 调用库
    im = Image.open("E:\demo.jpg")	   # 文件存在的路径 
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

### Image类中的方法

#### save

保存文件

```python
from PIL import Image
im = Image.open("E:\demo.jpg")
print(im)							  # 打印出原图片的详细信息
im.save("E:\demo.png")              # 将"E:\mywife.jpg"保存为"E:\mywife.png"
im = Image.open("E:\demo.png")   	# 打开新的png图片
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

#### convert

产生不同格式的图片并输出：

```python
from PIL import Image
im = Image.open("0000.jpg") # 读取图片
new_im = im.convert('1')	# 输出灰度图
print(new_im.mode)			 # 打印当前图像模式
new_im.show()				 # 显示转换之后的图片
```



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

