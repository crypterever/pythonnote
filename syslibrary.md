# sys库

sys模块包括了一组非常实用的服务，内含很多函数方法和变量，用来处理Python运行时配置以及资源，从而可以与前当程序之外的系统环境交互，如：`python`解释器。

## 常见函数列表：

| 函数                        | 说明                                                         |
| --------------------------- | ------------------------------------------------------------ |
| dir(sys)                    | dir()方法查看模块中可用的方法。注意：如果是在编辑器，一定要注意要事先声明代码的编码方式，否则中文会乱码。 |
| sys.argv                    | 实现从程序外部向程序传递参数                                 |
| sys.exit([arg])             | 程序中间的退出，arg=0为正常退出                              |
| sys.getdefaultencoding()    | 获取系统当前编码，一般默认为ascii                            |
| sys.setdefaultencoding()    | 设置系统默认编码，执行dir(sys)时不会看到这个方法，在解释器中执行不通过，可以先执行 |
| reload(sys)                 | 再执行setdefaultencoding(‘utf8’)，将系统编码设置为utf8       |
| sys.getfilesystemencoding() | 获取文件系统编码方式，Windows下返回’mbcs’，mac下返回’utf-8’  |
| sys.path                    | 获取指定模块搜索路径的字符串集合，可以将写好的模块放在得到的某个路径下，就可以在程序中import时正确找到 |
| sys.platform                | 获取当前系统平台。                                           |
| sys.stdin                   | sys.stdoutsys.stderr stdin，stdout，以及stderr变量包含与标准I/O流对应的流对象。如果需要更好地控制输出，而print不能满足要求，它们就是你所需要的。你也可以替换它们，重定向输出和输入到其它设备(device)，或者以非标准的方式处理它们。 |
| sys.modules                 | 是一个全局字典，该字典是python启动后就加载在内存中。每当程序员导入新的模块，sys.modules将自动记录该模块。当第二次再导入该模块时，python会直接到字典中查找，从而加快程序运行的速度。它拥有字典所拥有的一切方法。 |

