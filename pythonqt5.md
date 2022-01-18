# Python-GUI编程

## 01-什么是GUI编程？

### Graphical User Interface，简称 GUI

- 又称图形化用户接口

  - 会有一个图形化的界面展示给用户，与用户交互
  - 用户只需要鼠标点点点，手指戳戳戳就可以控制
  - 而不是，需要输入代码指令，以及接收枯燥的反馈等等

- 例如

  - 猜数字

    - 命令行界面版本
    - GUI界面版本

      - caishuzi.exe

  - 其他GUI界面举例

### 所谓的GUI编程，就是编写图形化界面的软件供用户使用

## 02-在Python中有哪些库可以支持GUI编程？

### 介绍文档

- https://wiki.python.org/moin/GuiProgramming

### 官方的标准库

- Tkinter

  - IDLE就是使用TKinter实现

### 其他使用率较高的库

- PyQt
- PySide
- wxPython 
- PyGUI
- Kivy
- Libavg
- ...

### 选库标准

- 表态

  - 没有最好的，只有最适合的

- 简单好用
- 功能强大

  - 看需求，有的仅仅需要最简单的界面

- 文档齐全，方便查看
- 性能高
- 稳定性高
- 生态支持

  - Qt助手
  - Qt设计师
  - ...

- 跨平台支持
- 开源免费

### 基于以上标准对比，最终选择PyQt

- PyQt是什么？

  - PyQt是Qt最流行的Python绑定之一

    - 简单理解

      - 使用Python重新实现了一遍Qt的功能

        - Python的语法简洁, 最终代码量更少
        - 阅读起来更容易理解

      - 在实现的时候, 几乎保持了全部原有的API

        - 学习完PyQt之后, 只要掌握C++语法之后, 
          就可以快速的接手Qt的使用

  - 本质还是Qt

    - c++写的一个跨平台的GUI开发框架
    - Qt发展

      - 1991年奇趣科技公司开发的C++ GUI应用程序
      - 2008年奇趣被诺基亚收购，Qt也就变成诺基亚的了
      - 2012年，Qt被Digia收购
      - 2014年发布了Qt5.3正式版，至此，对iOS，Android，WP等平台进行了全面支持
      - 现在提供了开源版本和商业版本

    - Qt官网

      - https://www1.qt.io/cn/

    - Qt功能

      - xml
      - 网络
      - 多线程
      - 数据库
      - 定位
      - 多媒体
      - web浏览器
      - 桌面UI

        - 主要讲解这一部分

      - ...

  - PyQt官网

    - https://www.riverbankcomputing.com/software/pyqt/intro

  - PyQt的版本

    - 1998年首次发布

      - PyKDE
      - 后改名PyQt

    - PyQt3
    - PyQt4
    - PyQt5

      - Python对Qt5.x版本的绑定
      - 对Python3支持很好

  - 环境版本选择

    - Python3 +
    - PyQt5

- PyQt优势

  - 简单好用

    - 在同等功能实现的下，使用已经很简单
    - 界面完全可以可视化操作

  - 功能强大

    - 600多个类
    - 种类繁多的控件

  - 跨平台支持

    - Windows
    - Linux
    - Mac OS
    - iOS
    - Android
    - ...

  - 性能高

    - Qt使用C++实现
    - 自行领悟

  - 文档齐全

    - 对Qt库Python绑定
    - 除下自己的文档，也几乎可以通用Qt文档

  - 稳定性高

    - 面向对象
    - 信号与槽的机制
    - 界面设计与业务代码完全隔离

  - 生态支持

    - Qt Designer进行图形界面设计
    - ui转换成py文件
    - 资源处理
    - ...

  - 开源免费

    - PyQt5是双重许可的。开发人员可以在GPL和商业许可之间进行选择
    - GPL协议

      - 软件版权为开发者本人所有
      - 受国际相关版权法保护
      - 允许其他用户对原作者软件进行复制和发行
      - 也可更改后，发行自己的软件
      - ...

## 03-开发环境安装

### 基本环境

- Python3.x解释器环境
- pip包管理工具
- pipenv虚拟环境管理工具

### IDE

- PyCharm安装

### GUI开发环境

- 全局安装

  - PyQt5安装

    - pip install PyQt5 -i https://pypi.douban.com/simple

  - 辅助工具安装

    - pip install PyQt5-tools -i https://pypi.douban.com/simple

- 虚拟环境安装

  - 创建虚拟环境（Python3.x版本解释器）

    - cd 项目路径
    - pipenv --three

  - 修改镜像

    - 清华：https://pypi.tuna.tsinghua.edu.cn/simple
    - Pipfile

  - 激活环境

    - pipenv shell

  - 安装三方库

    - pipenv install pyqt5
    - pipenv install pyqt5-tools

- 在线文档

  - http://pyqt.sourceforge.net/Docs/PyQt5/class_reference.html

### 测试

- 尝试导入包PyQt5，查看是否有问题
- from PyQt5.Qt import *

## 04-GUI编程应该学什么？

### 0. 大致了解你所选择的GUI库

- PyQt5

### 1. 基本程序结构

- 跑通GUI程序，能够看到一个界面

### 2. 各种控件的特性和使用

- 能够知道每个控件都有什么作用，能解决什么需求
- 知道该怎样去使用这个控件

### 3. 控件的样式

- 怎样能把控件的样式搞的好看一点，比如颜色，边框等等

### 4. 资源的加载

- 怎样加载资源，展示在GUI控件中

### 5. 控件的布局

- 怎样把各个单独的控件摆放的更协调，更美观

### 6. 事件和信号

- 怎样能够让用户点击或者做其他交互操作的时候，我们能让程序做事情

### 7. 动画特效

- 怎样能够在与用户交互的时候，展示炫酷的动画

### 8. 界面跳转

- 从一个窗口，跳转到另外一个窗口

### 9. 设计工具使用

- 通过辅助工具来设计界面

### 10. 额外

- 网络
- 多线程
- 数据库
- 文件操作
- 绘图
- 多媒体
- 定时器
- 定位
- 国际化
- ...

## 05-了解PyQt5库结构

### 文档

- http://pyqt.sourceforge.net/Docs/PyQt5/modules.html

### 常用模块

- QtWidgets

  - 包含了一整套UI元素控件，用于建立符合系统风格的界面

- QtGui

  - 涵盖了多种基本图形功能的类

    - 字体
    - 图形
    - 图标
    - 颜色
    - ...

- QtCore

  - 涵盖了包的核心的非GUI功能

    - 时间
    - 文件
    - 目录
    - 数据类型
    - 文本流
    - 链接
    - 线程进程
    - ...

- QtWebKit

  - 浏览器引擎

- QtTest

  - 测试

- QtSql

  - 数据库

- QtMultimedia
- QtMultimediaWidgets
- ...
- Qt

  - 将基本全部模块中的类综合到一个单一的模块中。
  - 好处

    - 不用关心哪个模块包含哪些类了

  - 坏处

    - 占用内存

## 06-PyQt5初体验-显示一个窗口

### 效果图

### 要求

- 展示一个500 * 500的窗口
- 设置窗口标题为“社会我顺哥，人狠话不多”
- 添加子控件(标签控件)，并显示"hello word"

### 方式

- 纯手码

## 07-PyQt5程序基本结构分析

### 面向过程版本代码

- import sys
- from PyQt5.Qt import *
- app = QApplication(sys.argv)
- window = QWidget()
- window.setWindowTitle("社会我顺哥,人狠话不多")
- window.resize(500, 500)
- window.move(400, 200)
- window.show()
- sys.exit(app.exec_())

### 解释

- 1. 一个PyQt程序都需要一个应用程序对象

  - 它包含主事件循环，在其中来自窗口系统和其它资源的所有事件被处理和调度。
  - 它也处理应用程序的初始化和结束，并且提供对话管理。
  - 它也处理绝大多数系统范围和应用程序范围的设置。

- 2. app.exec_()意思是让程序进入主循环，不要停止

- 3. 一个没有父对象控件默认不显示，必须要调用show()才可以

- 4. 一个应用程序中可以显示多个顶级控件

  - 如果一个Widget没有父控件，则认定为是顶级控件（顶级窗口）

    - 有标题栏，可以设置图标，标题
    - 有最大化，最小化，关闭等操作

  - 如果想要一个控件展示在另外一个控件内部，必须要有父子关系
  - 如果两个对象为父子关系，那么父对象显示之后，一般子对象会自动显示

### 补充

- PyCharm活动模板设置
- 面向对象版本代码

## 08-控件学习

### 什么是控件？

- 一个程序界面上的各个独立的元素

  - 一块矩形区域

- 具备不同的功能

  - 用户点击
  - 接收用户输入
  - 展示内容
  - 存放其他控件
  - ... ...

- 初识常用控件

  - 按钮

    - QPushButton
    - QCommandLinkButton
    - QRadioButton
    - QCheckBox

  - 输入控件

    - 纯键盘输入

      - QLineEdit
      - QTextEdit
      - QPlainTextEdit

      - QKeySequenceEdit

    - 步长调节(QAbstractSpinBox) (键盘+鼠标)

      - QDateTimeEdit

        - QDateEdit
        - QTimeEdit

      - QSpinBox
      - QDoubleSpinBox

    - 组合框(下拉选择输入)

      - QComboBox

        - QFontComboBox

    - 滑块(QAbstractSlider)(鼠标)

      - QDial
      - QSlider
      - QScrollBar

    - 橡皮筋选中

      - QRubberBand

    - 对话框(QDialog)

      - QColorDialog
      - QFileDialog
      - QFontDialog
      - QInputDialog

    - 日期

      - QCalendarWidget

  - 展示控件

    - QLabel

      - 效果图

        - 普通文本

        - 数字

        - 富文本

          - QLabel-超链接

        - 图片

        - QLabel-动画

    - QLCDNumber
    - QProgressBar
    - 对话框(QDialog)

      - QMessageBox

        - 效果图

      - QErrorMessage
      - QProgressDialog

  - 容器控件

    - QToolBox
    - QDialogButtonBox

      - 效果图

    - QGroupBox

      - 效果图

    - QMdiSubWindow

      - QMdiArea和QMdiSubWindow

  - 结构控件

    - QMainWindow

      - 效果图

      - 相关控件

        - QMenuBar

          - 相关控件

            - QMenu

        - QToolBar

          - 效果图

          - 相关控件

            - QToolButton

        - QStatusBar

          - 效果图

    - QTabwidget

      - 相关控件

        - QTabBar

    - QStackedWidget
    - QSplitter

      - 相关控件

        - QSplitterHandle

          - 效果图

    - QDockWidget

  - 滚动控件

    - QAbstractScrollArea

      - QTextBrowser
      - QScrollArea
      - QAbstractItemView

        - QColumnView
        - QHeaderView

          - 效果图

        - QListView

          - QListWidget
          - QUndoView

        - QTableView

          - 效果图

          - QTableWidget

        - QTreeView

          - QTreeWidget

      - QMdiarea
      - QGraphicsView

  - 辅助控件

    - QFocusFrame

      - 效果图

    - QSizeGrip

      - 效果图

    - QDesktopWidget

      - 效果图

  - 其他

    - 向导/打印(QDialog)

      - QWizard

        - 相关控件

          - QWizardPage

      - QAbstractPrintDialog

        - QPrintDialog

          - 效果图

      - QPrintPreviewDialog

        - 效果图

        - 相关控件

          - QPrintPreviewWidget

      - QPageSetupDialog

        - 效果图

    - 欢迎界面QSplashScreen

      - QSplashScreen

    - 功能性控件

      - QVideoWidget

        需要下载解码器

        http://www.codecguide.com/configuration_tips.htm?version=1430

        - QCameraViewfinder

          - 效果图

      - QWebEngineView

        - 效果图

- 不同的控件有

  - 相同的共性

    - 名字
    - 矩形区域
    - 位置
    - 大小
    - 可以设置样式
    - ...

  - 不同的特性

    - 展示内容
    - 接收输入
    - 用户交互
    - 容器
    - 框架
    - ...

### 类继承图(了解)

### 基类(共性)

- QObject

  - QWidget

    - QAbstractButton

      - QPushButton

    - QFrame

      - QAbstractScrollArea

        - QAbstractItemView

          - QListView
          - QTableView
          - QTreeView

        - QTextEdit

    - QAbstractSpinBox
    - QAbstractSlider
    - QComboBox
    - QDialog

### 子类(特性)

- 基础控件

  - 按钮

    - QPushButton

      - 描述

        - 用来给用户点击, 来完成某种动作的控件

          - 一般是矩形

        - 例如

          - 登录按钮
          - 注册按钮
          - 关闭按钮
          - 是
          - 否
          - ...

      - 继承

        - QAbstractButton

      - 功能作用

        - 创建按钮控件

          - QPushButton()

            - 创建一个无父控件的按钮控件

          - QPushButton(parent)

            - 创建控件的同时, 设置父控件

          - QPushButton(text, parent)

            - 创建控件的同时, 设置提示文本和父控件

          - QPushButton(icon, text, parent)

            - 创建控件的同时, 设置图标, 提示文本和父控件

        - 菜单

          - API

            - setMenu(QMenu)

              - 设置菜单

            - menu()

              - 获取菜单

            - showMenu()

              - 展示菜单

          - 应用场景

            - 可以设置点击按钮是弹出的菜单， 供用户选择

          - 案例

            - 测试以上API

          - 补充

            - QMenu

              - 添加子菜单

                - addMenu(QMenu)

              - 添加分割线

                - addSeparator()

              - 添加行为动作

                - addAction(QAction)

              - QMenu控件设置

                - setTitle(str)
                - setIcon(QIcon)

              - QAction设置

                - setText(str)
                - setIcon(QIcon)
                - 信号

                  - triggered

        - 边框是否保持扁平

          - API

            - setFlat(bool)

              - 默认值为False
              - 设置了此属性，则除非按下按钮，否则大多数样式都不会绘制按钮背景

            - isFlat()

              - 获取当前按钮边框是否扁平

          - 应用场景

            - 设置按钮扁平化风格

          - 案例

            - 测试以上API

        - 默认处理

          - API

            - setAutoDefault(bool)

              - 设置为自动默认按钮
              - 在某些GUI样式中，默认按钮被绘制，其周围有一个额外的框架，最多3个像素或更多。
              - Qt会自动在自动默认按钮周围保留此空间，即自动默认按钮可能会有稍大的提示
              - 对于具有QDialog父级的按钮，此属性的默认值为true ; 否则默认为false。

            - autoDefault()
            - setDefault(bool)
            - isDefault()

          - 应用场景

            - 一般是在对话框中使用

          - 案例

            - 测试以上API

      - 信号

        - 都是继承下来的
        - QAbstractButton

          - pressed()

            - 鼠标按下信号

          - released()

            - 鼠标释放

              - 控件内松开鼠标
              - 鼠标移出控件范围后松开

          - clicked(checked = false)

            - 控件内按下+控件内释放

          - toggled(bool checked)

            - 切换信号(一般在单选框或者复选框中使用)

        - QWidget

          - windowTitleChanged(QString)

            - 窗口标题改变信号

          - windowIconChanged(QIcon)

            - 窗口图标改变信号

          - customContextMenuRequested(QPoint)

            - 自定义上下文菜单请求信号

              - setContextMenuPolicy(Qt.CustomContextMenu)
              - Qt.DefaultContextMenu

                - 调用对象方法contextMenuEvent()

              - Qt.CustomContextMenu

                - 发射信号

    - QCommandLinkButton

      - 描述

        - 命令链接是Windows Vista引入的新控件
        - 它的用途类似于单选按钮的用途，因为它用于在一组互斥选项之间进行选择
        - 命令链接按钮不应单独使用，而应作为向导和对话框中单选按钮的替代选项
        - 外观通常类似于平面按钮的外观，但除了普通按钮文本之外，它还允许描述性文本

      - 继承

        - QPushButton

      - 功能作用

        - 创建命令链接按钮

          - QCommandLinkBut​​ton(parent)
          - QCommandLinkBut​​ton(text, parent)
          - QCommandLinkBut​​ton(text, description ,parent)

        - 描述设置

          - API

            - setDescription(str)
            - description()

          - 应用场景

            - 设置命令链接按钮的描述文本

          - 案例

            - 测试以上API

      - 信号

        - 看他老爸去

    - QToolButton

      - 描述

        - 提供了一个快速访问按钮
        - 通常是在工具栏内部使用
        - 工具按钮通常不显示文本标签，而是显示图标
        - 例如

      - 继承

        - QAbstractButton

      - 功能作用

        - 创建按钮

          - QToolButton(parent: QWidget = None)

        - (继承)设置文本,图标,工具提示

          - API

            - setText(str)
            - setIcon(QIcon)
            - setIconSize(QSize)
            - setToolTip(str)

          - 注意

            - 如果文本和图标同时设置, 则默认只展示图标

          - 案例

            - 测试以上API

        - 按钮样式风格

          - API

            - setToolButtonStyle(Qt.ToolButtonStyle)

              - 风格取值

                - Qt.ToolButtonIconOnly

                  - 仅显示图标

                - Qt.ToolButtonTextOnly

                  - 仅显示文字

                - Qt.ToolButtonTextBesideIcon

                  - 文本显示在图标旁边

                - Qt.ToolButtonTextUnderIcon

                  - 文本显示在图标下方

                - Qt.ToolButtonFollowStyle

                  - 遵循风格

            - toolButtonStyle()

          - 应用场景

            - 设置按钮的图标和文字组合

          - 案例

            - 测试以上API

        - 设置箭头

          - API

            - setArrowType(Qt.ArrowType)

              - Qt.ArrowType

                - Qt.NoArrow

                  - 无箭头

                - Qt.UpArrow

                  - 向上箭头

                - Qt.DownArrow

                  - 向下箭头

                - Qt.LeftArrow

                  - 向左箭头

                - Qt.RightArrow

                  - 向右箭头

            - arrowType()

          - 应用场景

            - 将按钮变成一个具备特殊箭头图标的按钮

          - 案例

            - 测试以上API

        - 自动提升

          - API

            - setAutoRaise(bool)
            - autoRaise()

          - 应用场景

            - 在自动提升模式下，该按钮仅在鼠标指向时才会绘制3D帧
            - 在工具栏(QToolBar)中, 默认就是自动提升

          - 案例

            - 测试以上API

        - 菜单

          - API

            - setMenu(QMenu)
            - menu()

          - 应用场景

            - 通过菜单展示更多选项

          - 案例

            - 测试以上API

        - 菜单弹出模式

          - API

            - setPopupMode(QToolButton.ToolButtonPopupMode)

              - QToolButton.ToolButtonPopupMode

                - QToolButton.DelayedPopup

                  - 鼠标按住一会才显示
                  - 类似于浏览器后退按钮

                - QToolButton.MenuButtonPopup

                  - 有一个专门的指示箭头
                  - 点击箭头才显示

                - QToolButton.InstantPopup

                  - 点了按钮就显示
                  - 点击信号不会发射

            - popupMode()

          - 应用场景

            - 设置菜单弹出的触发方式

          - 案例

            - 测试以上API

      - 信号

        - triggered(QAction *action)

          - 当点击某个action时触发, 并会将action传递出来
          - 小技巧

            - QAction对象可以通过

              - setData(Any)

                - 绑定数据

              - data()

                - 获取数据

        - 其他都是继承的

    - QRadioButton

      - 描述

        - 一般用于给用户提供若干选项中的单选操作

          - 比如

            - 性别

              - 男
              - 女

            - 答案

              - 是
              - 否

            - ...

          - 当选中一个时, 会自动取消上一个

        - 此按钮左侧会有一个圆圈图标, 用于标识用户的选中状态

      - 继承

        - QAbstractButton

      - 功能作用

        - 创建单选按钮

          - QRadioButton(parent)
          - QRadioButton(text, parent)

        - 常用继承父类操作

          - 图标

            - setIcon(QIcon)

          - 快捷键

            - 文本加&
            - setShortcut()

      - 信号

        - 均继承自父类
        - 常用信号为

          - toggled(bool)

    - QCheckBox

      - 描述

        - 一般用于给用户提供若干选项中的多选操作

          - 比如

            - 兴趣爱好

              - Python
              - C++
              - ...

            - 点外卖加配料

              - 酱油
              - 辣椒
              - 醋
              - ...

          - 可以都选, 可以都不选, 可以选部分

        - 左侧会有一个方框图标, 标识用户的选中状态

      - 继承

        - QAbstractButton

      - 功能作用

        - 创建复选框按钮

          - QCheckBox(parent=None)
          - QCheckBox(text, parent=None)

        - 常用继承父类操作

          - 图标

            - setIcon(QIcon)

          - 快捷键

            - 文本加&
            - setShortcut()

        - 设置是否三态

          - API

            - setTristate(bool=True)
            - isTristate()

          - 应用场景

            - 是否支持复选框展示三种状态

        - 设置复选框状态

          - API

            - setCheckState(Qt.CheckState)
            - checkState()

          - 应用场景

            - 想给用户多一种选择状态

        - 补充

          - 状态

            - Qt.Unchecked

              - 该项目未选中

            - Qt.PartiallyChecked

              - 部分选中

            - Qt::Checked

              - 真的被选中

      - 信号

        - stateChanged(int state)

          - 选中或清除选中时, 发射此信号

        - 其他都继承

    - 补充

      - QButtonGroup

        - 描述

          - 提供 一个抽象的按钮容器, 可以将多个按钮划分为一组
          - 不具备可视化的效果
          - 一般放的都是可以被检查的按钮

        - 继承

          - QObject

        - 功能

          - 创建按钮组

            - QButtonGroup(parent)

          - 添加按钮

            - API

              - addButton(QAbstractButton, id = -1)

                - 如果id为-1，则将为该按钮分配一个id。自动分配的ID保证为负数，从-2开始。
                - 如果要分配自己的ID，请使用正值以避免冲突

            - 应用场景

              - 向按钮组中添加按钮, 并选择性设置ID

          - 查看按钮

            - API

              - buttons()

                - 查看所有按钮组中的按钮

              - button(ID)

                - 根据ID获取对应按钮, 没有则返回None

              - checkedButton()

                - 获取选中的那个按钮

            - 应用场景

              - 获取指定条件的按钮

          - 移除按钮

            - API

              - removeButton(QAbstractButton)

            - 应用场景

              - 移除指定按钮
              - 注意

                - 不是从界面上移除
                - 是从抽象关系上移除

          - 绑定和获取ID

            - API

              - setId(QAbstractButton，int)
              - id(QAbstractButton)

                - 指定按钮对应的ID
                - 如果不存在此按钮，则返回-1

              - checkedId()

                - 选中的ID
                - 如果没有选中按钮则返回-1

            - 应用场景

              - 设置ID, 方便识别用户选项

          - 独占设置

            - API

              - setExclusive(bool)
              - exclusive()

            - 应用场景

              - 统一设置按钮组中的按钮是否是独占(选择互斥)

        - 信号

          - buttonClicked(int/QAbstractButton)

            - 当按钮组中的按钮被点击时, 发射此信号

          - buttonPressed(int/QAbstractButton)

            - 当按钮组中的按钮被按下时, 发射此信号

          - buttonReleased(int/QAbstractButton)

            - 当按钮组中的按钮被释放时, 发射此信号

          - buttonToggled(QAbstractButton/int, bool)

            - 当按钮组中的按钮被切换状态时, 发射此信号

          - 重点注意

            - 如果一个对象向外界提供的信号名称一样, 但参数不一样
            - 外界在使用信号时, 可以使用如下格式进行选择
            - signal_name[type]

              - signal_name

                - 信号名称

              - type

                - 参数类型

  - 输入控件

    - 纯键盘文本输入

      - QLineEdit

        - 描述

          - 是一个单行文本编辑器
          - 允许用户输入和编辑单行纯文本
          - 自带一组编辑功能

            - 编辑功能

              - 撤消
              - 重做
              - 剪切
              - 粘贴
              - 拖放

        - 继承

          - QWidget

        - 功能作用

          - 控件的创建

            -     QLineEdit(parent: QWidget = None)
            -     QLineEdit(str, parent: QWidget = None)

          - 文本的设置和获取

            - API

              - setText(str)

                - 设置内容文本

              - insert(newText)

                - 在光标处插入文本

              - text()

                - 获取真实内容文本

              - displayText()

                - 获取用户能看到的内容文本

            - 应用场景

              - 通过代码来控制输入文本内容

            - 案例

              - 创建一个窗口, 添加两个文本框一个按钮

                - 要求

                  - 点击按钮后

                    - 将文本框A内输入的内容
                    - 复制到文本框B中

          - 输出模式

            - API

              - setEchoMode(QLineEdit.EchoMode)

                - QLineEdit.EchoMode

                  -     NoEcho = 1

                        - 不输出

                  -     Normal = 0

                        - 正常输出

                  -     Password = 2

                        - 密文形式

                  -     PasswordEchoOnEdit = 3

                        - 编辑时明文, 结束后密文

              - echoMode() -> QLineEdit.EchoMode

                - 获取输出模式

            - 应用场景

              - 设置输出模式, 来适应不同的应用场景

                - 明文
                - 密文

                  - 保护用户隐私

                - 不输出

            - 案例

              - 模拟用户登录案例
              - 创建一个窗口, 添加两个文本框一个按钮

                - 要求

                  - 一个用作账号
                  - 另外一个用作密码
                  - 点击登录按钮后, 获取账号和密码信息
                  - 进行比对账号密码信息

                    - 正确账号

                      - sz

                    - 正确密码

                      - itlike

                    - 如果账号错误, 则清空账号框和密码框
                    - 密码错误则清空密码框

          - 占位提示字符串

            - API

              - setPlaceholderText(notice_str)
              - placeholderText()

            - 应用场景

              - 在用户输入文本内容之前, 给用户的提示语句
              - 文本框内容

                - 空

                  - 显示提示文本

                - 不空

                  - 隐藏提示文本

            - 案例

              - 完善上述案例

                - 添加账号和密码输入提示

          - 清空按钮显示

            - API

              - setClearButtonEnabled(bool)
              - isClearButtonEnabled() -> bool

            - 应用场景

              - 用作快速清空文本框内容

            - 案例

              - 完善上述案例

                - 为密码文本框添加清空按钮

          - 添加操作行为

            - API

              - addAction(QAction, QLineEdit.ActionPosition)

                -  QLineEdit.ActionPosition

                   - QLineEdit.LeadingPosition

                     - 搁前面

                   - QLineEdit.TrailingPosition

                     - 搁后面

              - addAction(QIcon, QLineEdit.ActionPosition) -> QAction

            - 应用场景

              - 为文本框添加附加的行为操作

            - 案例

              - 完善上述案例

                - 为密码文本框添加明文和密文切换按钮
                - 图片素材

          - 自动补全

            - API

              - setCompleter(QCompleter)

                - 设置完成器

              - completer() -> QCompleter

            - 应用场景

              - 根据用户已输入的字符串, 快速联想补全

            - 案例

              - 完善上述案例

                - 为账号文本框, 设置补全候选项

                  - Sz
                  - shehui
                  - wangzha

          - 输入限制

            - API

              - 内容长度限制

                - setMaxLength(int)

                  - 设置限制输入的长度

                - maxLength()

                  - 获取输入长度

              - 只读限制

                - setReadOnly(bool)
                - isReadOnly()

              - 规则验证

                - setValidator(QValidator)

                  - 设置验证器

                - setInputMask(mask_str)

                  - 掩码验证

              - 判定输入文本是否通过验证

                - hasAcceptableInput()

            - 应用场景

              - 限制用户在文本框中输入的内容

            - 案例

              - 测试以上API

            - 补充

              - QValidator

                - 描述

                  - 验证器

                    - 用于验证用户输入数据的合法性

                  - 如果一个输入框设置了验证器

                    - 到时用户在文本框中输入内容时
                    - 首先会将内容传递给验证器进行验证

                      - validate(self, input_text, pos)

                        - return (QValidator.Acceptable,  input_text, pos)

                          - 验证通过

                        - return (QValidator.Intermediate,  input_text, pos)

                          - 暂不作判定是否通过验证

                        - return (QValidator.Invalid,  input_text, pos)

                          - 验证不通过

                    - 如果输入框结束输入后, 上述的验证状态并非有效, 则会调用修复方法

                      - fixup(self, input_text)

                        - return 修正后文本

                  - 是一个抽象类, 使用前需要进行子类化操作

                    - 自定义子类
                    - 系统提供子类

                      - QIntValidator(bottom, top, parent)

                        - 限制整型数据范围

                      - QDoubleValidator

                        - 浮点类型数据限制范围
                        - 经测试, 无效

                          - 需要手动实现

                      - QRegExpValidator

                        - 通过正则表达式限定

                - 基本使用

                  - 第一步

                    - 子类化此类

                  - 第二步

                    - 实现

                      - validate(self, input_text, pos)

                        - return (QValidator.Acceptable,  input_text, pos)

                          - 验证通过

                        - return (QValidator.Intermediate,  input_text, pos)

                          - 暂不作判定是否通过验证

                        - return (QValidator.Invalid,  input_text, pos)

                          - 验证不通过

                      - fixup(self, input_text)

                        - return 修正后文本

              - 掩码含义

                - 掩码可以指定固定位置的固定数据类型, 达到一个格式上的限制
                - 例如

                  - 座机号码

                    - 四位区号-七位电话

                  - IP地址

                    - XXX.XXX.XXX.XXX

                - 掩码由一串掩码字符和分隔符组成

                  - +

                    - 可选的分号; 和 空白占位字符

                - 掩码字符含义

          - 是否被编辑

            - API

              - isModified()
              - setModified(bool)

            - 应用场景

              - 标识文本内容是否被修改

            - 案例

              - 测试以上API

          - 光标控制

            - API

              - cursorBackward(bool mark，int steps = 1)

                - 向后(左)移动steps个字符

                  - mark: True

                    - 带选中效果

                  - mark: False

                    - 不带选中效果

              - cursorForward(bool mark，int steps = 1)

                - 向前(右)移动steps个字符

                  - mark: True

                    - 带选中效果

                  - mark: False

                    - 不带选中效果

              - cursorWordBackward(bool mark)

                - 向后(左)移动一个单词长度

                  - mark: True

                    - 带选中效果

                  - mark: False

                    - 不带选中效果

              - cursorWordForward(bool mark)

                - 向前(右)移动一个单词长度

                  - mark: True

                    - 带选中效果

                  - mark: False

                    - 不带选中效果

              - home(bool)

                - 移动到行首

                  - True

                    - 带选中

                  - False

                    - 不带选中

              - end(bool)

                - 移动到行尾

                  - True

                    - 带选中

                  - False

                    - 不带选中

              - setCursorPosition(int)

                - 设置光标位置

              - cursorPosition()

                - 获取光标位置

              - cursorPositionAt(const QPoint＆ pos)

                - 获取指定坐标位置对应文本光标位置

            - 应用场景

              - 控制光标, 以及文本选中操作

            - 案例

              - 测试以上API

          - 文本边距设置

            - API

              - getTextMargins()
              - setTextMargins(int left，int top，int right，int bottom)

            - 应用场景

              - 设置文本内容边距

            - 案例

              - 测试以上API

          - 对齐方式

            - API

              - setAlignment(Qt.Alignment)

                - 设置输入文本的对齐方式
                - Qt.Alignment

                  - 水平

                    - Qt.AlignLeft
                    - Qt.AlignRight
                    - Qt.AlignHCenter
                    - Qt.AlignJustify

                      - 此处同左对齐

                  - 垂直

                    - Qt.AlignTop
                    - Qt.AlignBottom
                    - Qt.AlignVCenter
                    - Qt.AlignBaseline

                  - Qt.AlignCenter

                    - 等同于

                      - Qt.AlignHCenter | Qt.AlignVCenter

                    - 垂直和水平都居中

              - alignment() -> Qt.Alignment

            - 应用场景

              - 设置用户输入的内容文本对齐方式

            - 案例

              - 测试上述API

          - 常用编辑功能

            - API

              - 退格

                - backspace()

                  - 删除选中文本

                    - 如果有

                  - 或
                  - 删除光标左侧一个字符

              - 删除

                - del_()

                  - 删除选中文本

                    - 如果有

                  - 或
                  - 删除光标右侧的一个字符

              - 清空

                - clear()

                  - 删除所有文本框内容

              - 复制

                - copy()

              - 剪切

                - cut()

              - 粘贴

                - paste()

              - 撤消

                - isUndoAvailable()
                - undo()

              - 重做

                - isRedoAvailable()
                - redo()

              - 拖放

                - setDragEnabled(bool)

                  - 设置选中文本后是否可以拖拽

              - 文本选中

                - setSelection(start_pos, length)

                  - 选中指定区间的文本

                - selectAll()

                  - 选中所有文本

                - deselect()

                  - 取消选中已选择文本

                - hasSelectedText()

                  - 是否有选中文本

                - selectedText() -> str

                  - 获取选中的文本

                - selectionStart() -> int

                  - 选中的开始位置

                - selectionEnd() -> int

                  - 选中的结束位置

                - selectionLength() -> int

                  - 选中的长度

            - 应用场景

              - 编辑用户输入的文本

            - 案例

              - 测试上述API

        - 信号

          - textEdited( text)

            - 文本编辑时发射的信号

          - textChanged(text)

            - 文本框文本发生改变时发出的信号

          - returnPressed()

            - 按下回车键时发出的信号

          - editingFinished()

            - 结束编辑时发出的信号

          - cursorPositionChanged(int oldPos，int newPos)

            - 光标位置发生改变时发出的信号

          - selectionChanged()

            - 选中的文本发生改变时发出的信号

      - QTextEdit

        - 描述

          - 是一个高级的WYSIWYG(What You See Is What You Get 所见即所得)查看器/编辑器，支持使用HTML样式标签的富文本格式。

            - 支持的HTML4标签子集
            - https://doc.qt.io/qt-5/richtext-html-subset.html
            - 如果不够, 可以考虑使用WebKit

          - 它经过优化，可以处理大型文档并快速响应用户输入。
          - 适用于段落和字符

            - 如果文本太大而无法在文本编辑的视口中查看，则会出现滚动条

          - 文本编辑可以加载纯文本和富文本文件

            - 以显示图像，列表和表格

        - 继承

          - QAbstractScrollArea

        - 功能作用

          - 占位提示文本

            - API

              - setPlaceholderText(str)
              - placeholderText() -> str

            - 应用场景

              - 在文本框内部内容为空时, 给用户的文本提示信息

            - 案例

              - 测试以上API

          - 内容设置

            - API

              - 普通文本

                - setPlainText(str)
                - insertPlainText(str)
                - toPlainText() -> str

              - HTML

                - setHtml(str)
                - insertHtml(str)
                - toHtml() -> str

              - 设置文本(自动判定)

                - setText(str)

              - 追加文本

                - append(str)

              - 清空

                - clear()

              - 文本光标

                - 理论基础

                  - 通过文本光标, 可以操作编辑 文本文档 对象

                    - 概念

                      - 整个文本编辑器, 其实就是为编辑 这个文本文档 提供了一个可视化的界面
                      - 简单理解, 可以比喻成 一个doc文档, 使用word软件打开了这个文档, 你可以随意编辑

                    - 获取文本文档的方法

                      - API

                        - te.document() -> QTextDocument

                      - 补充

                        - QTextDocument

                          - 描述

                            - 保存带格式的文本文档
                            - 为样式化文本和各种类型的文档元素提供支持

                              - 框架
                              - 文本块
                              - 列表
                              - 表格
                              - 图像
                              - ...

                            - 是结构化富文本文档的容器

                              - 一个空的文档包含一个根框架，这个框架包含一个空的文本块

                                - 当需要进行文档结构导航时，有时候可以从根框架开始。
                                - 因为根框架提供了访问整个文档结构的能力

                            - 文本属性在字符级别和块级别定义

                              - 在字符级别可以指定字体、颜色和大小
                              - 在块级别可以指定更高一级的行为，例如文本流方向、对齐方式和背景色

                          - 继承结构图

                            - QTextDocument
                            - QTextObject

                              - QTextBlockGroup

                                - QTextList

                              - QTextFrame

                                - QTextTable

                            - QTextBlock
                            - QTextFormat

                              - QTextBlockFormat
                              - QTextCharFormat

                                - QTextImageFormat
                                - QTextTableCellFormat

                              - QTextFrameFormat

                                - QTextTableFormat

                              - QTextListFormat

                - textCursor() -> QTextCursor

                  - 常用功能

                    - 添加内容

                      - API

                        - 插入文本

                          - insertText(str)

                            - 插入文本(普通文本)

                          - insertText(QString text, QTextCharFormat format)

                            - 插入文本, 带格式
                            - QTextCharFormat

                              - 针对于部分字符的格式描述

                          - insertHtml(html_str)

                            - 插入HTML 字符串

                        - 插入图片

                          - insertImage(QTextImageFormat)

                            - QTextImageFormat

                              -     tf.setName("xxx.png")
                              -     tf.setWidth(20)
                              -     tf.setHeight(20)

                          - insertImage(QTextImageFormat, QTextFrameFormat.Position)
                          - insertImage(name_str)
                          - insertImage(QImage, name_str=None)

                        - 插入句子

                          - insertFragment(QTextDocumentFragment )

                            - QTextDocumentFragment

                              - 构建对象

                                - fromHtml(html_str)
                                - fromPlainText(str)

                        - 插入列表

                          - insertList(QTextListFormat) -> QTextList 

                            - 在当前位置插入一个新块，并使其成为具有给定格式的新创建列表的第一个列表项。返回创建的列表

                          - insertList(QTextListFormat.Style) -> QTextList

                            - 在当前位置插入一个新块，并使其成为具有给定格式的新创建列表的第一个列表项。返回创建的列表

                          - createList(QTextListFormat ) -> QTextList 

                            - 创建并返回具有给定格式的新列表，并使当前段落的光标位于第一个列表项中

                          - createList(QTextListFormat.style ) -> QTextList 

                            - 创建并返回具有给定格式的新列表，并使当前段落的光标位于第一个列表项中

                          - 补充

                            - QTextListFormat

                              - setIndent(int)
                              - setNumberPrefix(str)
                              - setNumberSuffix(str)
                              - setStyle(QTextListFormat_Style)

                            - QTextListFormat.Style

                              - QTextListFormat.ListDisc

                                - 一个圆圈

                              - QTextListFormat.ListCircle

                                - 一个空的圆圈

                              - QTextListFormat.ListSquare

                                - 一个方块

                              - QTextListFormat.ListDecimal

                                - 十进制值按升序排列

                              - QTextListFormat.ListLowerAlpha

                                - 小写拉丁字符按字母顺序排列

                              - QTextListFormat.ListUpperAlpha

                                - 大写拉丁字符按字母顺序排列

                              - QTextListFormat.ListLowerRoman

                                - 小写罗马数字（仅支持最多4999项）

                              - QTextListFormat.ListUpperRoman

                                - 大写罗马数字（仅支持最多4999项）

                        - 插入表格

                          - insertTable(int rows, int columns) -> QTextTable 
                          - insertTable(int rows, int columns, QTextTableFormat) -> QTextTable 
                          - 补充

                            - QTextTableFormat

                              - setAlignment(self, Union, Qt_Alignment=None, Qt_AlignmentFlag=None)

                                - 对齐方式

                              - setCellPadding(self, p_float)

                                - 内边距

                              - setCellSpacing(self, p_float)

                                - 外边距

                              - setColumnWidthConstraints(self, Iterable, QTextLength=None)

                                - 设置列宽

                              - 边距图示

                        - 插入文本块

                          - insertBlock()

                            - 插入一个空的文本块

                          - insertBlock(QTextBlockFormat)

                            - 插入文本块的同时, 设置文本块格式

                          - insertBlock(QTextBlockFormat, QTextCharFormat )

                            - 插入文本块的同时, 设置文本块格式和文本字符格式

                        - 插入框架

                          - insertFrame(QTextFrameFormat) -> QTextFrame

                      - 应用场景

                        - 插入指定格式的内容元素

                      - 案例

                        - 测试以上API

                    - 设置和合并格式

                      - API

                        - setBlockCharFormat(QTextCharFormat)

                          - 设置要格式化的当前块（或选择中包含的所有块）的块char 格式

                        - setBlockFormat(QTextBlockFormat)

                          - 设置当前块的块格式（或选择中包含的所有块）以进行格式化

                        - setCharFormat(QTextCharFormat)

                          - 将光标的当前字符格式设置为给定格式。如果光标有选择，则给定格式应用于当前选择

                        - mergeBlockCharFormat(QTextCharFormat)

                          - 合并当前块的char格式

                        - mergeBlockFormat(QTextBlockFormat)

                          - 合并当前块的格式

                        - mergeCharFormat(QTextCharFormat)

                          - 合并当前字符格式

                      - 应用场景

                        - 设置和合并格式

                      - 案例

                        - 测试以上API

                    - 获取内容和格式相关

                      - API

                        - block() -> QTextBlock

                          - 获取光标所在的文本块

                        - blockFormat() -> QTextBlockFormat

                          - 获取光标所在的文本块格式

                        - blockCharFormat() -> QTextCharFormat

                          - 获取光标所在的文本块字符格式

                        - blockNumber() -> int

                          - 获取光标所在的文本块编号

                        - charFormat() -> QTextCharFormat

                          - 获取文本字符格式

                        - currentFrame() -> QTextFrame

                          - 获取当前所在的框架

                        - currentList() -> QTextList 

                          - 获取当前所在的文本列表

                        - currentTable() -> QTextTable 

                          - 获取当前的表格

                      - 应用场景

                        - 通过文本光标获取当前所在的内容和格式信息

                      - 案例

                        - 测试以上API

                    - 文本选中和清空

                      - API

                        - 选中

                          - setPosition(int pos, QTextCursor.MoveMode=MoveAnchor)

                            - 设置光标位置
                            - 需要反向设置回去

                          - movePosition(QTextCursor.MoveOperation, QTextCursor.MoveMode=MoveAnchor, int n = 1)

                            - 移动指定长度后, 参照移动选项和模式确定最终位置以及是否选中文本
                            - 需要反向设置

                          - select(QTextCursor.SelectionType)

                            - 需要反向设置

                        - 选中内容获取

                          - selectedText() -> str
                          - selection() -> QTextDocumentFragment
                          - selectedTableCells() -> (int firstRow, int numRows, int firstColumn, int numColumns)

                        - 选中的位置获取

                          - selectionStart() -> int
                          - selectionEnd() -> int

                        - 清空和判定

                          - clearSelection()

                            - 取消文本的选中
                            - 需要反向设置

                          - hasSelection() -> bool

                            - 是否有选中文本

                        - 选中文本的移除

                          - removeSelectedText()

                            - 移除选中的文本

                        - 补充

                          - QTextCursor.MoveMode

                            - QTextCursor.MoveAnchor

                              - 将锚点移动到与光标本身相同的位置。

                            - QTextCursor.KeepAnchor

                              - 将锚固定在原处。

                          - QTextCursor.MoveOperation

                            - QTextCursor.NoMove

                              - 将光标保持在原位

                            - QTextCursor.Start

                              - 移至文档的开头。

                            - QTextCursor.StartOfLine

                              - 移动到当前行的开头。

                            - QTextCursor.StartOfBlock

                              - 移动到当前块的开头。

                            - QTextCursor.StartOfWord

                              - 移动到当前单词的开头。

                            - QTextCursor.PreviousBlock

                              - 移动到上一个块的开头。

                            - QTextCursor.PreviousCharacter

                              - 移至上一个字符。

                            - QTextCursor.PreviousWord

                              - 移到上一个单词的开头。

                            - QTextCursor.Up

                              - 向上移动一行。

                            - QTextCursor.Left

                              - 向左移动一个字符。

                            - QTextCursor.WordLeft

                              - 向左移动一个单词。

                            - QTextCursor.End

                              - 移到文档的末尾。

                            - QTextCursor.EndOfLine

                              - 移动到当前行的末尾。

                            - QTextCursor.EndOfWord

                              - 移到当前单词的末尾。

                            - QTextCursor.EndOfBlock

                              - 移动到当前块的末尾。

                            - QTextCursor.NextBlock

                              - 移动到下一个块的开头。

                            - QTextCursor.NextCharacter

                              - 移动到下一个角色。

                            - QTextCursor.NextWord

                              - 转到下一个单词。

                            - QTextCursor.Down

                              - 向下移动一行。

                            - QTextCursor.Right

                              - 向右移动一个角色。

                            - QTextCursor.WordRight

                              - 向右移动一个单词。

                            - QTextCursor.NextCell	

                              - 移动到当前表中下一个表格单元格的开头。如果当前单元格是行中的最后一个单元格，则光标将移动到下一行中的第一个单元格。

                            - QTextCursor.PreviousCell

                              - 移动到当前表内的上一个表格单元格的开头。如果当前单元格是行中的第一个单元格，则光标将移动到上一行中的最后一个单元格。

                            - QTextCursor.NextRow

                              - 移动到当前表中下一行的第一个新单元格。

                            - QTextCursor.PreviousRow

                              - 移动到当前表中上一行的最后一个单元格。

                          - QTextCursor.SelectionType

                            - QTextCursor.Document

                              - 选择整个文档。

                            - QTextCursor.BlockUnderCursor

                              - 选择光标下的文本块。

                            - QTextCursor.LineUnderCursor

                              - 选择光标下的文本行。

                            - QTextCursor.WordUnderCursor

                              - 选择光标下的单词。如果光标未定位在可选字符串中，则不选择任何文本。

                      - 应用场景

                        - 通过文本光标对象来操作输入框内容

                      - 案例

                        - 测试以上API

                    - 删除内容

                      - API

                        - deleteChar()

                          - 如果没有选中文本, 删除文本光标后一个字符
                          - 如果有选中文本, 则删除选中文本

                        - deletePreviousChar()

                          - 如果没有选中文本, 删除文本光标前一个字符
                          - 如果有选中文本, 则删除选中文本

                      - 应用场景

                        - 删除单个字符

                      - 案例

                        - 测试以上API

                    - 位置相关

                      - API

                        - atBlockEnd()

                          - 是否在文本块末尾

                        - atBlockStart()

                          - 是否在文本块开始

                        - atEnd()

                          - 是否在文档末尾

                        - atStart()

                          - 是否在文档开始

                        - columnNumber() -> int

                          - 在第几列

                        - position()

                          - 光标位置

                        - positionInBlock() 

                          - 在文本块中的位置

                      - 应用场景

                        - 获取和判定光标的位置

                      - 案例

                        - 测试以上API

                    - 开始和结束编辑标识

                      - API

                        - beginEditBlock()
                        - endEditBlock()

                      - 应用场景

                        - 指示文档上的编辑操作块的开始，
                        - 该操作应从撤消/重做的角度显示为单个操作。

                      - 案例

                        - 测试以上API

            - 应用场景

              - 设置与获取文本信息

            - 案例

              - 测试以上API

          - 自动格式化

            - API

              - setAutoFormatting(QTextEdit.AutoFormatting)

                - QTextEdit.AutoFormatting

                  - QTextEdit.AutoNone

                    - 不要做任何自动格式化。

                  - QTextEdit.AutoBulletList

                    - 自动创建项目符号列表（例如，当用户在最左侧列中输入星号（'*'）时，或在现有列表项中按Enter键。

                  - QTextEdit.AutoAll

                    - 应用所有自动格式。目前仅支持自动项目符号列表。

              - autoFormatting() -> QTextEdit.AutoFormatting

            - 应用场景

              - 输入一些特定字符, 会转换成为对应的效果

            - 案例

              - 测试以上API

          - 软换行模式

            - API

              - setLineWrapMode(QTextEdit.LineWrapMode)

                - 设置软换行模式

              - lineWrapMode() -> QTextEdit.LineWrapMode

                - 获取软换行模式

              - setWordWrapMode(self, QTextOption.WrapMode)

                - 设置单词换行模式

              - wordWrapMode(self) -> QTextOption.WrapMode

                - 获取单词换行模式

              - 补充

                - QTextEdit.LineWrapMode

                  - QTextEdit.NoWrap

                    - 没有软换行, 超过宽度后, 会产生水平滚动条

                  - QTextEdit.WidgetWidth

                    - 以控件的宽度为限制
                    - 但会保持单词的完整性

                  - QTextEdit.FixedPixelWidth

                    - 填充像素宽度
                    - 配合

                      - setLineWrapColumnOrWidth(int)
                      - lineWrapColumnOrWidth() -> int

                  - QTextEdit.FixedColumnWidth

                    - 填充列的宽度
                    - 配合

                      - setLineWrapColumnOrWidth(int)
                      - lineWrapColumnOrWidth() -> int

                - QTextOption.WrapMode

                  - QTextOption.NoWrap

                    - 文本根本没有包装。

                  - QTextOption.WordWrap

                    - 保持单词完整性

                  - QTextOption.ManualWrap

                    - 与QTextOption.NoWrap相同

                  - QTextOption.WrapAnywhere

                    - 宽度够了之后, 随意在任何位置换行

                  - QTextOption.WrapAtWordBoundaryOrAnywhere

                    - 尽可能赶在单词的边界, 否则就在任意位置换行

            - 应用场景

              - 设置当用户输入内容过多时, 是否进行软换行, 以及如何进行软换行

            - 案例

              - 测试以上API

          - 覆盖模式

            - API

              - setOverwriteMode(bool)
              - overwriteMode() -> bool

            - 应用场景

              - 切换覆盖模式, 修改文本内容

            - 案例

              - 测试以上API

          - 光标设置

            - API

              - 光标宽度

                - setCursorWidth(int)
                - cursorWidth()

              - 光标矩形

                - cursorRect() -> QRect

            - 应用场景

              - 一般是结合覆盖模式来做, 标识光标的宽度, 给用户以提醒

            - 案例

              - 测试下, 以后有需求直接用

          - 对齐方式

            - API

              - setAlignment(Qt.Alignment)

                - 常用有效对齐是

                  - Qt.AlignLeft
                  - Qt.AlignRight
                  - Qt.AlignCenter

              - alignment() -> Qt.Alignment

            - 应用场景

              - 设置当前段落的对齐方式

            - 案例

              - 测试以上API

          - 字体格式

            - API

              - 字体家族

                - setFontFamily(family_str)
                - fontFamily()
                - 小技巧

                  - QFontDialog.getFont()
                  - 查看可用的字体

              - 字体样式

                - 字体粗细

                  - setFontWeight(int)

                    - QFont.Thin
                    - QFont.ExtraLight
                    - QFont.Light
                    - QFont.Normal
                    - QFont.Medium
                    - QFont.DemiBold
                    - QFont.Bold
                    - QFont.ExtraBold
                    - QFont.Black

                  - fontWeight()

                - 字体斜体

                  - setFontItalic(bool)
                  - fontItalic()

              - 字体尺寸

                - setFontPointSize(float)
                - fontPointSize()

              - 字体效果

                - 字体下划线

                  - setFontUnderline(bool)
                  - fontUnderline()

              - 统一设置QFont

                - setCurrentFont(QFont)
                - currentFont() -> QFont

            - 应用场景

              - 设置当前文本框内容字体样式

            - 案例

              - 测试以上API

          - 颜色设置

            - API

              - 背景颜色

                - setTextBackgroundColor(QColor)

                  - 将当前格式的文本背景颜色设置为指定颜色

                - textBackgroundColor() -> QColor

              - 文本颜色

                - setTextColor(QColor)

                  - 将当前格式的文本颜色设置为指定颜色

                - textColor() -> QColor

            - 应用场景

              - 修改文本前景色以及背景色

            - 案例

              - 测试以上API

          - 当前的字符格式

            - API

              - setCurrentCharFormat(QTextCharFormat)
              - mergeCurrentCharFormat(QTextCharFormat)
              - currentCharFormat() -> QTextCharFormat

            - 应用场景

              - 针对于部分字符, 设置特定的格式
              - 将新文本插入格式时使用的char格式。
              - 如果编辑器有选择的文本内容，则char格式直接应用于选择

            - 案例

              - 测试以上API

            - 补充

              - QTextCharFormat

                - 描述

                  - 提供了一种字符格式信息
                  - 文档中文本的字符格式指定文本的可视属性，以及有关其在超文本文档中的角色的信息

                - 常用功能作用

                  - 字体

                    - 统一设置

                      - setFont(QFont)
                      - font() -> QFont

                    - 字体家族

                      - setFontFamily(family_str)
                      - fontFamily() -> str

                    - 字体大小

                      - setFontPointSize(float)
                      - fontPointSize() -> float

                    - 字体粗细

                      - setFontWeight(int)
                      - fontWeight() -> int

                    - 字体上划线

                      - setFontOverline(bool)
                      - fontOverline() -> bool

                    - 字体中划线

                      - setFontStrikeOut(bool)
                      - fontStrikeOut() -> bool

                    - 字体下划线

                      - setFontUnderline(bool)
                      - fontUnderline() -> bool

                    - 字体大小写

                      - setFontCapitalization(QFont.Capitalization)
                      - fontCapitalization() -> QFont.Capitalization

                        - QFont.MixedCase

                          - 这是正常的文本呈现选项，不应用大写更改。

                        - QFont.AllUppercase

                          - 这会改变要以全大写类型呈现的文本。

                        - QFont.AllLowercase

                          - 这会改变要以全小写类型呈现的文本。

                        - QFont.SmallCaps

                          - 这会改变要以小型大写字母呈现的文本。

                        - QFont.Capitalize

                          - 这会将要呈现的文本更改为每个单词的第一个字符作为大写字符。

                  - 颜色

                    - setForeground(QColor(100, 200, 150))

                  - 超链接

                    - setAnchorHref("http://www.itlike.com")
                    - anchorHref() -> str

                  - ...

          - 常用编辑操作

            - API

              - copy()
              - paste()
              - canPaste() -> bool
              - setUndoRedoEnabled(bool)
              - redo()
              - undo()
              - selectAll()
              - find(str, options: Union[QTextDocument.FindFlags, QTextDocument.FindFlag] = QTextDocument.FindFlags()) -> bool

                - QTextDocument.FindBackward

                  - 向后搜索而不是向前搜索。

                - QTextDocument.FindCaseSensitively

                  - 默认情况下，查找工作区不区分大小写。
                  - 指定此选项会将行为更改为区分大小写的查找操作。

                - QTextDocument.FindWholeWords

                  - 使查找匹配仅完整的单词。

            - 应用场景

              - 常用内容文档编辑操作

          - 滚动

            - scrollToAnchor(p_str)
            - 注意

              - 锚点设置

                - <a name="锚点名称" href="#锚点内容"> xxx </a>

          - 只读设置

            - setReadOnly(self, bool)
            - isReadOnly() -> bool

          - tab控制

            - setTabChangesFocus(bool)

              - 控制Tab键位的功能, 是否是改变焦点
              - 默认是False

            - setTabStopDistance(p_float)

              - 制表位的距离

                - 默认80(像素)

            - setTabStopWidth(p_int)

              - 经测试, 同上

            - tabStopDistance(self) -> float

              - 获取距离

            - tabStopWidth() -> int

              - 获取宽度

          - 锚点获取

            - API

              - anchorAt(QPoint) -> str

            - 应用场景

              - 返回位置pos处的锚点的引用，如果该点处不存在锚点，则返回空字符串

            - 案例

              - 单击超链接后, 打开对应的网页

            - 补充

              - QDesktopServices.openUrl(QUrl(urlString))

                - 打开指定链接地址

        - 信号

          - textChanged()

            - 文本内容发生改变时, 发射的信号

          - selectionChanged()

            - 选中内容发生改变时, 发射的信号

          - cursorPositionChanged()

            - 光标位置发生改变时, 发射的信号

          - currentCharFormatChanged(QTextCharFormat)

            - 当前额字符格式发生改变时, 发射的信号

          - copyAvailable(bool yes)

            - 复制可用时

          - redoAvailable(bool available)

            - 重做可用时

          - undoAvailable(bool available)

            - 撤销可用时

      - QPlainTextEdit

        - 描述

          - QPlainText和QTextEdit大致功能实现差不多

            - 适用于段落和字符

              - 段落是一个格式化的字符串,为了适应控件的宽度, 会自动换行
              - 默认情况下，在读取纯文本时，一个换行符表示一个段落。
              - 文档由零个或多个段落组成。段落由硬线断开分隔。
              - 段落中的每个字符都有自己的属性，例如字体和颜色。

            - 内容的编辑

              - 文本的选择由QTextCursor类处理，该类提供创建选择，检索文本内容或删除选择的功能
              - QPlainTextEdit包含一个QTextDocument对象，可以使用document（）方法检索该对象

          - 但针对纯文本处理进行了优化
          - 与QTextEdit的差异

            - QPlainTextEdit是一个简略版本的类

              - 使用QTextEdit和QTextDocument作为背后实现的技术支撑

            - 它的性能优于QTextEdit, 主要是因为在文本文档中使用QPlainTextDocumentLayout简化文本布局
            - 纯文本文档布局不支持表格或嵌入框架，并使用逐行逐段滚动方法替换像素精确高度计算。

        - 继承

          - QAbstractScrollArea

        - 功能作用

          - 构造函数

            -     QPlainTextEdit(parent: QWidget = None)
            -     QPlainTextEdit(str, parent: QWidget = None)

          - 占位提示文本

            - API

              - setPlaceholderText(str)
              - placeholderText() -> str

            - 应用场景

              - 在文本框内部内容为空时, 给用户的文本提示信息

            - 案例

              - 测试以上API

          - 只读设置

            - API

              - setReadOnly(bool)
              - isReadOnly() -> bool

            - 应用场景

              - 控制文本框只读

            - 案例

              - 测试以上API

          - 格式

            - API

              - currentCharFormat() -> QTextCharFormat
              - setCurrentCharFormat(QTextCharFormat)
              - mergeCurrentCharFormat(QTextCharFormat)

            - 应用场景

              - 字符格式的控制

            - 案例

              - 测试以上API

          - 软换行模式

            - API

              - lineWrapMode() -> QPlainTextEdit.LineWrapMode
              - setLineWrapMode(QPlainTextEdit.LineWrapMode)

            - 应用场景

              - 设置文本内容超过控件宽度时, 是否进行自动换行

            - 案例

              - 测试以上API

            - 补充

              - QPlainTextEdit.LineWrapMode

                - QPlainTextEdit.NoWrap

                  - 没有软换行

                - QPlainTextEdit.WidgetWidth

                  - 超出控件宽度进行自动换行

          - 覆盖模式

            - API

              - overwriteMode() -> bool
              - setOverwriteMode(bool)

            - 应用场景

              - 控制是否采用覆盖模式编辑文本

            - 案例

              - 测试以上API

          - Tab控制

            - API

              - setTabChangesFocus(bool)
              - setTabStopDistance(distance_float)
              - tabChangesFocus() -> bool
              - tabStopDistance() -> float

            - 应用场景

              - 控制Tab的作用, 以及对应的距离

            - 案例

              - 测试以上API

          - 文本操作

            - API

              - setPlainText(text_str)

                - 设置普通文本内容

              - insertPlainText(text_str)

                - 插入普通文本

              - appendPlainText(text_str)

                - 追加普通文本

              - appendHtml(html_str)

                - 追加HTML字符串
                - 注意

                  - 有些标签不支持

                    - 表格
                    - 列表
                    - 图片
                    - ...

              - toPlainText() -> 转换成纯文本

            - 应用场景

              - 追加以及获取文本

            - 案例

              - 测试以上API

          - 块操作

            - API

              - blockCount() -> int

                - 当前块个数

              - maximumBlockCount() -> int

                - 最大块个数

              - setMaximumBlockCount(int)

                - 设置最大块个数

            - 应用场景

              - 设置用户能够输入的最大块数

            - 案例

              - 测试以上API

          - 常用编辑操作

            - API

              - selectAll()

                - 选中所有

              - copy()

                - 复制选中文本

              - cut()

                - 剪切选中文本

              - paste()

                - 粘贴文本
                - canPaste() -> bool

                  - 判定是否可以粘贴

              - clear()

                - 清空内容

              - redo()

                - 重做
                - isUndoRedoEnabled() -> bool

                  - 判定撤销重做是否可用

                - setUndoRedoEnabled(bool)

                  - 设置撤销重做是否可用

              - undo()

                - 撤销

              - find(str, QTextDocument.FindFlags) -> bool

                - QTextDocument.FindBackward

                  - 向后搜索而不是向前搜索。

                - QTextDocument.FindCaseSensitively

                  - 默认情况下，查找工作区不区分大小写。
                  - 指定此选项会将行为更改为区分大小写的查找操作。

                - QTextDocument.FindWholeWords

                  - 使查找匹配仅完整的单词。

              - zoomIn(int range = 1)

                - 放大缩小

                  - range > 0

                    - 放大

                  - range < 0

                    - 缩小

              - zoomOut(int range = 1)

                - 过期
                - 效果和上面的方法相反

            - 应用场景

              - 快速完成编辑操作

            - 案例

              - 测试以上API

          - 滚动

            - API

              - centerCursor()

                - 控制光标, 尽可能保证光标在文本框中间

              - ensureCursorVisible()

                - setCenterOnScroll(bool)

                  - 传递True

                    - 表示, 控制光标(包括尾部), 显示时能够展示在中间位置
                    - 注意

                      - 必须事先设置好

                - centerOnScroll() -> bool
                - 滚动控件, 确保光标可见

            - 应用场景

              - 控制文本框的内容滚动

            - 案例

              - 测试以上API

          - 光标

            - textCursor() -> QTextCursor

              - 获取文本光标对象

            - cursorForPosition(QPoint) -> QTextCursor

              - 获取指定位置的文本光标对象

            - cursorWidth() -> int

              - 获取文本光标宽度
              - setCursorWidth(int)

                - 设置文本光标宽度

            - cursorRect() -> QRect

              - 获取文本光标矩形
              - cursorRect(QTextCursor)

                - 获取指定光标对象的矩形

            - moveCursor(QTextCursor.MoveOperation，QTextCursor.MoveMode)

              - QTextCursor.MoveOperation

                - QTextCursor.NoMove

                  - 将光标保持在原位

                - QTextCursor.Start

                  - 移至文档的开头。

                - QTextCursor.StartOfLine

                  - 移动到当前行的开头。

                - QTextCursor.StartOfBlock

                  - 移动到当前块的开头。

                - QTextCursor.StartOfWord

                  - 移动到当前单词的开头。

                - QTextCursor.PreviousBlock

                  - 移动到上一个块的开头。

                - QTextCursor.PreviousCharacter

                  - 移至上一个字符。

                - QTextCursor.PreviousWord

                  - 移到上一个单词的开头。

                - QTextCursor.Up

                  - 向上移动一行。

                - QTextCursor.Left

                  - 向左移动一个字符。

                - QTextCursor.WordLeft

                  - 向左移动一个单词。

                - QTextCursor.End

                  - 移到文档的末尾。

                - QTextCursor.EndOfLine

                  - 移动到当前行的末尾。

                - QTextCursor.EndOfWord

                  - 移到当前单词的末尾。

                - QTextCursor.EndOfBlock

                  - 移动到当前块的末尾。

                - QTextCursor.NextBlock

                  - 移动到下一个块的开头。

                - QTextCursor.NextCharacter

                  - 移动到下一个角色。

                - QTextCursor.NextWord

                  - 转到下一个单词。

                - QTextCursor.Down

                  - 向下移动一行。

                - QTextCursor.Right

                  - 向右移动一个角色。

                - QTextCursor.WordRight

                  - 向右移动一个单词。

                - QTextCursor.NextCell	

                  - 移动到当前表中下一个表格单元格的开头。如果当前单元格是行中的最后一个单元格，则光标将移动到下一行中的第一个单元格。

                - QTextCursor.PreviousCell

                  - 移动到当前表内的上一个表格单元格的开头。如果当前单元格是行中的第一个单元格，则光标将移动到上一行中的最后一个单元格。

                - QTextCursor.NextRow

                  - 移动到当前表中下一行的第一个新单元格。

                - QTextCursor.PreviousRow

                  - 移动到当前表中上一行的最后一个单元格。

              - QTextCursor.MoveMode

                - QTextCursor.MoveAnchor

                  - 将锚点移动到与光标本身相同的位置。

                - QTextCursor.KeepAnchor

                  - 将锚固定在原处。

        - 信号

          - textChanged()

            - 文本改变时

          - selectionChanged()

            - 选中内容改变时

          - modificationChanged(bool)

            - 编辑状态改变时

          - cursorPositionChanged()

            - 光标位置改变时

          - blockCountChanged(int)

            - 块的个数发生改变时

          - updateRequest(QRect rect, int dy)

            - 内容更新请求时

          - copyAvailable(bool)

            - 复制可用时

          - redoAvailable(bool)

            - 重做可用时

          - undoAvailable(bool)

            - 撤销可用时

      - QKeySequenceEdit

        - 描述

          - 控件允许输入QKeySequence, 它通常用作快捷方式。
          - 当控件收到焦点时开始录制，并在用户释放最后一个关键字后一秒钟结束录制

        - 继承

          - QWidget

        - 功能作用

          - 快捷键

            - setKeySequence(QKeySequence keySequence)
            - keySequence() -> QKeySequence

          - 清除

            - clear()

        - 信号

          - editingFinished()

            - 结束编辑时发射

          - keySequenceChanged(QKeySequence  keySequence)

            - 键位序列改变时发射

        - 补充

          - QKeySequence

            - 描述

              - 用来描述一个键位序列
              - 键位序列描述了必须一起使用以执行某些操作的键组合
              - 键位序列分类

                - 标准键位序列(QKeySequence.)

                  - HelpContents	F1
                  - WhatsThis	Shift+F1
                  - Open	Ctrl+O
                  - Close	Ctrl+F4, Ctrl+W
                  - Save	Ctrl+S
                  - Quit		Ctrl+Q
                  - SaveAs		Ctrl+Shift+S
                  - New	Ctrl+N
                  - Delete	Del
                  - Cut	Ctrl+X, Shift+Del	
                  - Copy	Ctrl+C, Ctrl+Ins
                  - Paste	Ctrl+V, Shift+Ins
                  - Preferences		Ctrl+,
                  - Undo	Ctrl+Z, Alt+Backspace
                  - Redo	Ctrl+Y, Shift+Ctrl+Z, Alt+Shift+Backspace
                  - Back	Alt+Left, Backspace
                  - Forward	Alt+Right, Shift+Backspace
                  - Refresh	             F5	
                  - ZoomIn	Ctrl+Plus
                  - ZoomOut	Ctrl+Minus
                  - FullScreen	F11, Alt+Enter
                  - Print	Ctrl+P
                  - AddTab	Ctrl+T
                  - NextChild	Ctrl+Tab, Forward, Ctrl+F6
                  - PreviousChild	Ctrl+Shift+Tab, Back, Ctrl+Shift+F6
                  - Find	Ctrl+F
                  - FindNext	F3, Ctrl+G
                  - FindPrevious	Shift+F3, Ctrl+Shift+G
                  - Replace	Ctrl+H
                  - SelectAll	Ctrl+A
                  - Deselect	Ctrl+Shift+A
                  - Bold	Ctrl+B
                  - Italic	Ctrl+I
                  - Underline	Ctrl+U
                  - MoveToNextChar	Right
                  - MoveToPreviousChar	Left
                  - MoveToNextWord	Ctrl+Right
                  - MoveToPreviousWord	Ctrl+Left
                  - MoveToNextLine	Down
                  - MoveToPreviousLine	Up
                  - MoveToNextPage	PgDown
                  - MoveToPreviousPage	PgUp
                  - MoveToStartOfLine	Home
                  - MoveToEndOfLine	End
                  - MoveToStartOfDocument	Ctrl+Home
                  - MoveToEndOfDocument	Ctrl+End
                  - SelectNextChar	Shift+Right
                  - SelectPreviousChar	Shift+Left
                  - SelectNextWord	Ctrl+Shift+Right
                  - SelectPreviousWord	Ctrl+Shift+Left
                  - SelectNextLine	Shift+Down
                  - SelectPreviousLine	Shift+Up
                  - SelectNextPage	Shift+PgDown
                  - SelectPreviousPage	Shift+PgUp
                  - SelectStartOfLine	Shift+Home
                  - SelectEndOfLine	Shift+End
                  - SelectStartOfDocument	Ctrl+Shift+Home
                  - SelectEndOfDocument	Ctrl+Shift+End
                  - DeleteStartOfWord	Ctrl+Backspace
                  - DeleteEndOfWord	Ctrl+Del
                  - InsertParagraphSeparator	Enter
                  - InsertLineSeparator	Shift+Enter
                  - Cancel	Escape

                - 自定义键位序列

                  - 字符串

                    - "Ctrl+S"

                  - 枚举值

                    - Qt.Ctrl + Qt.Key_S

                - 注意

                  - 1. 优先使用标准键位序列
                  - 2. 自定义键位序列, 保证可读, 尽可能不用枚举值对应的整形数据

            - 功能作用

              - 构造函数

                - QKeySequence(key_str)
                - QKeySequence(QKeySequence.StandardKey key)
                - QKeySequence(int k1, int k2 = 0, int k3 = 0, int k4 = 0)
                - 静态方法

                  - fromString(key_str)

              - 转换成可读字符串

                - toString() -> str

              - 键位个数

                - count()

    - 步长调节(QAbstractSpinBox) (键盘+鼠标)

      - QSpinBox

        - 描述

          - 主要处理整数和离散值集

            - 1--99
            - 1月--12月
            - 周一--周日

          - 允许用户通过单击向上/向下按钮或按键盘上的上/下来选择一个值来增加/减少当前显示的值。用户还可以手动键入值
          - 旋转框支持整数值

            - 也可以子类化此类实现更多支持

        - 继承

          - QAbstractSpinBox

        - 功能作用

          - 构造函数

            - QSpinBox(parent: QWidget = None)
            - 默认功能

              - 调整0到99范围之间的整数

                - 步长调节器
                - 修改文本框内容

          - 设置数值范围

            - API

              - setMaximum(max_num)

                - 设置最大值
                - maximum() -> int

              - setMinimum(min_num)

                - 设置最小值
                - minimum() -> int

              - setRange(min_num, max_num)

                - 设置数值区间

            - 应用场景

              - 控制数据的范围

            - 案例

              - 测试以上API

          - 数值循环

            - API

              - setWrapping(bool)
              - wrapping() -> bool

            - 应用场景

              - 设置数值达到最大/小时, 跳转到最小/大

            - 案例

              - 测试以上API

          - 设置步长

            - API

              - setSingleStep(step_int)
              - singleStep() -> int

            - 应用场景

              - 设置步长调节器, 单步步长值

            - 案例

              - 测试以上API

          - 前缀和后缀

            - API

              - setPrefix("周")

                - 设置前缀作为展示
                - prefix() -> str

              - setSuffix("月")

                - 设置后缀作为展示
                - suffix() -> str

            - 应用场景

              - 特定场景下, 设置前缀或者后缀
              - 年月日, 星期

            - 案例

              - 测试以上API

          - 最小值特殊文本

            - API

              - setSpecialValueText(str)

                - 父类中的方法
                - 当数据到达最小值时, 会显示此字符串

            - 应用场景

              - 设置特殊含义的数值字符串

            - 案例

              - 测试以上API

          - 显示基数(进制)

            - API

              - setDisplayIntegerBase(int)

                - 默认是10

              - displayIntegerBase() -> int

            - 应用场景

              - 控制文本框内容的显示基数
              - 以几进制的形式进行展示

            - 案例

              - 测试以上API

          - 设置和获取数值

            - API

              - setValue(int)
              - value() -> int
              - cleanText() -> str

            - 应用场景

              - 设置以及获取数据

            - 案例

              - 测试以上API

          - 自定义展示格式

            - API

              - 重写

                - textFromValue(self, p_int) -> format_str

            - 应用场景

              - 展示数值之前, 调用此方法, 转换成对应的格式字符串进行展示

            - 案例

              - 测试以上API

        - 信号

          - valueChanged(int i)
          - valueChanged(QString text)

            - 重载

      - QDoubleSpinBox

        - 描述

          - 浮点类型步长调节器

            - 0.00 - 99.99
            - 1.00 % - 99.99 %

          - 既可以通过步长调节器调整数据, 也可以通过文本框直接编辑

        - 继承

          - QAbstractSpinBox

        - 功能作用

          - 构造函数

            - QDoubleSpinBox(parent: QWidget = None)
            - 默认功能

              - 步长为1.0, 调整0.00到99.99范围之间的浮点数

                - 步长调节器
                - 修改文本框内容

          - 设置数值范围

            - API

              - setMaximum(max_num)

                - 设置最大值
                - maximum() -> float

              - setMinimum(min_num)

                - 设置最小值
                - minimum() -> float

              - setRange(min_num, max_num)

                - 设置数值区间

            - 应用场景

              - 控制数据的范围

            - 案例

              - 测试以上API

          - 数值循环

            - API

              - setWrapping(bool)
              - wrapping() -> bool

            - 应用场景

              - 设置数值达到最大/小时, 跳转到最小/大

            - 案例

              - 测试以上API

          - 设置步长

            - API

              - setSingleStep(step_float)
              - singleStep() -> float

            - 应用场景

              - 设置步长调节器, 单步步长值

            - 案例

              - 测试以上API

          - 前缀和后缀

            - API

              - setPrefix("$")

                - 设置前缀作为展示
                - prefix() -> str

              - setSuffix("%")

                - 设置后缀作为展示
                - suffix() -> str

            - 应用场景

              - 特定场景下, 设置前缀或者后缀
              - 年月日, 星期

            - 案例

              - 测试以上API

          - 最小值特殊文本

            - API

              - setSpecialValueText(str)

                - 父类中的方法
                - 当数据到达最小值时, 会显示此字符串

            - 应用场景

              - 设置特殊含义的数值字符串

                - 1.0

                  - 正常

                - 1.5
                - 2.0

            - 案例

              - 测试以上API

          - 设置小数位数

            - API

              - setDecimals(int)
              - decimals() -> int

            - 应用场景

              - 设置支持更高精度的数据

            - 案例

              - 测试以上API

          - 设置和获取数值

            - API

              - setValue(float)

                - 如果设置的小数位数过多, 则会按照真实位数四舍五入

              - value() -> float

                - 真实的数值

              - cleanText() -> str

                - 旋转框的文本，不包括任何前缀，后缀或前导或尾随空格

            - 应用场景

              - 设置以及获取数据

            - 案例

              - 测试以上API

          - 自定义展示格式

            - API

              - 重写

                - textFromValue(self, p_int) -> format_str

            - 应用场景

              - 展示数值之前, 调用此方法, 转换成对应的格式字符串进行展示

            - 案例

              - 测试以上API

        - 信号

          - valueChanged(float)
          - valueChanged(QString text)

            - 重载

      - QDateTimeEdit

        - 描述

          - 编辑日期和时间的单行文本框
          - 既可以用箭头调节, 也可以用键盘编辑输入
          - 可以单独调节某个部分

        - 继承

          - QAbstractSpinBox

        - 功能作用

          - 构造函数

            - API

              - QDateTimeEdit(parent: QWidget = None)
              - QDateTimeEdit(Union[QDateTime, datetime.datetime], parent: QWidget = None)
              - QDateTimeEdit(Union[QDate, datetime.date], parent: QWidget = None)
              - QDateTimeEdit(Union[QTime, datetime.time], parent: QWidget = None)

            - 应用场景

              - 根据指定日期或时间, 创建出日期时间编辑器控件
              - 并会初始化该控件展示的section

            - 案例

              - 测试以上API

          - 显示格式

            - API

              - setDisplayFormat(format_str)

                - 设置日期时间显示格式

              - displayFormat() -> str

                - 获取日期时间显示格式

            - 应用场景

              - 设置展示的section格式

            - 案例

              - 测试以上API

          - section控制

            - API

              - sectionCount() -> int

                - 获取section个数

              - setCurrentSectionIndex(int)

                - 设置当前的section索引

              - currentSectionIndex() -> int

                - 获取section索引

              - setCurrentSection(QDateTimeEdit.Section)

                - 设置当前操作的日期时间section

              - currentSection() -> QDateTimeEdit.Section

                - 获取当前的section部分

              - sectionAt(index_int) -> QDateTimeEdit.Section

                - 获取指定索引位置的section

              - sectionText(QDateTimeEdit.Section) -> str

                - 获取指定section的文本内容

              - 00-01-01 $ 0: 01: 000

            - 应用场景

              - 控制section部分

            - 案例

              - 测试以上API

            - 补充

              - QDateTimeEdit.Section

                - QDateTimeEdit.NoSection
                - QDateTimeEdit.AmPmSection
                - QDateTimeEdit.MSecSection
                - QDateTimeEdit.SecondSection
                - QDateTimeEdit.MinuteSection
                - QDateTimeEdit.HourSection
                - QDateTimeEdit.DaySection
                - QDateTimeEdit.MonthSection
                - QDateTimeEdit.YearSection

          - 最大和最小日期时间

            - API

              - 日期时间

                - 最大

                  - setMaximumDateTime(QDateTime)

                    - 默认

                      - 9999年12月31日 23:59:59 999毫秒

                  - maximumDateTime() -> QDateTime
                  - clearMaximumDateTime()

                - 最小

                  - setMinimumDateTime(QDateTime)
                  - minimumDateTime() -> QDateTime
                  - clearMinimumDateTime()

                - 范围

                  - setDateTimeRange(min_datetime, max_datetime)

              - 日期

                - 最大

                  - setMaximumDate(QDate)

                    - 设置最大日期
                    - 默认包含9999年12月31日

                  - maximumDate() -> QDate

                    - 获取最大日期

                  - clearMaximumDate()

                    - 清除自定义最大日期, 恢复默认

                - 最小

                  - setMinimumDate(QDate)

                    - 设置最小日期
                    - 默认1752年9月14日

                  - minimumDate() -> QDate

                    - 获取最小日期

                  - clearMinimumDate()

                    - 清除自定义最小日期, 恢复默认

                - 范围

                  - setDateRange(min_date, max_date)

              - 时间

                - 最大

                  - setMaximumTime(QTime)
                  - maximumTime() -> QTime
                  - clearMaximumTime()

                - 最小

                  - setMinimumTime(QTime)
                  - minimumTime() -> QTime
                  - clearMinimumTime()

                - 范围

                  - setTimeRange(min_time, max_time)

            - 应用场景

              - 控制日期范围

            - 案例

              - 测试以上API

          - 日历选择控件

            - API

              - 是否弹出日历选择控件

                - setCalendarPopup(bool)
                - calendarPopup()

              - 自定义日历选择控件

                - setCalendarWidget(QCalendarWidget)
                - calendarWidget() -> QCalendarWidget

            - 应用场景

              - 通过日历选择控件, 快速的让用户输入日期

            - 案例

              - 测试以上API

          - 获取日期和时间

            - API

              - dateTime() -> QDateTime
              - date() -> QDate
              - time() -> QTime

            - 应用场景

              - 获取用户所输入的日期时间

            - 案例

              - 测试以上API

        - 信号

          - dateTimeChanged(QDateTime datetime)
          - dateChanged(QDate date)
          - timeChanged(QTime time)

        - 补充

          - QDateTime

            - 描述

              - 日期时间对象
              - 它是QDate和QTime类的组合
              - 包括年月日 时分秒毫秒

            - 功能作用

              - 日期时间对象构造

                -     QDateTime()
                -     QDateTime(QDateTime)
                -     QDateTime(QDate)
                -     QDateTime(QDate,  QTime, Qt.TimeSpec = Qt.LocalTime)
                -     QDateTime(int, int, int, int, int, second: int = 0, msec: int = 0, timeSpec: int = 0)
                -     QDateTime(QDate, QTime, Qt.TimeSpec, int)
                -     QDateTime(QDate, QTime, QTimeZone)
                -     静态方法

                      - currentDateTime()

                        - 当前时间

                      - currentDateTimeUtc()

                        - 世界标准时间

              - 调整日期时间

                - addYears(int)
                - addMonths(int)
                - addDays(int)
                - addSecs(int)
                - addMSecs(int)
                - setDate(const QDate &date)
                - setTime(const QTime &time)

              - 计算时间差

                - offsetFromUtc()
                - secsTo(QDateTime)
                - msecsTo(QDateTime)

          - QDate

            - 描述

              - 日期对象
              - 包括年月日

            - 功能作用

              - 日期对象的构造

                - QDate()
                - QDate(int y, int m, int d)
                - currentDate()

              - 调整日期

                - setDate(int year, int month, int day)
                - addYears(int nyears)
                - addMonths(int nmonths)
                - addDays(qint64 ndays)

              - 计算时间差

                - daysTo(const QDate &d)

              - 获取时间

                - day()

                  - 这一个月的第几日

                - month()

                  - 第几月

                - year() 

                  - 第几年

                - dayOfWeek()

                  - 这一周 第几日

                - dayOfYear()

                  - 这一年 第几日

                - daysInMonth()

                  - 这一月总共多少天

                - daysInYear()

                  - 这一年总共多少天

          - QTime

            - 描述

              - 时间对象
              - 包括时分秒毫秒

            - 功能作用

              - 时间对象构造

                - QTime()
                - QTime(int h, int m, int s = 0, int ms = 0)
                - currentTime()

              - 调整时间

                - addSecs(int s)
                - addMSecs(int ms)

              - 计算时间差

                - secsTo(QTime t) 

              - 计时

                -  start()
                -  restart()
                -  elapsed()

                   - 以上两个方法启动后, 至此方法调用时, 经历的毫秒数

              - 获取时间

                - hour()
                - minute()
                - second() 
                - msec()

          - 时间日期格式符

            - 日期

              - d

                - 没有前导零的数字的日期（1到31）

              - dd

                - 有前导零的数字的日期（01到31）

              - ddd

                - 缩写的本地化日期名称（例如'Mon'到'Sun'

              - dddd

                - 完整本地化的日期名称（例如“星期一”到“星期日”）

              - M

                - 没有前导零的数字的月份（1-12）

              - MM

                - 月份为前导零的数字（01-12）

              - MMM

                - 缩写的本地化月份名称（例如'Jan'到'Dec'）

              - MMMM

                - 完整的本地化月份名称（例如“1月”到“12月”）

              - yy

                - 年份为两位数字（00-99）

              - yyyy

                - 年份为四位数字

            - 时间

              - h

                - 没有前导零的小时（如果显示AM / PM，则为0到23或1到12）

              - hh

                - 前导零的小时（如果AM / PM显示，则为00到23或01到12）

              - H

                - 没有前导零的小时（0到23，即使有AM / PM显示）

              - HH

                - 前导零的小时（00到23，即使有AM / PM显示）

              - m

                - 没有前导零的分钟（0到59）

              - mm

                - 前导零（00到59）的分钟

              - s

                - 整个秒没有前导零（0到59）

              - ss

                - 带有前导零（00到59）

              - z

                - 第二个小数部分, 没有尾随零的毫秒（0到999）

              - zzz

                - 第二个小数部分, 有尾随零的毫秒（000到999）

              - AP / A

                - 使用AM / PM显示

              - ap / a

                - 使用am / pm显示

              - t

                - 时区

        - 相关子类

          - QDateEdit

            - 描述

              - 基于QDateTimeEdit控件的小控件
              - 主要操作日期部分

            - 继承

              - QDateTimeEdit

            - 功能作用

              - 构造函数

                - QDateEdit(QWidget *parent = nullptr)
                - QDateEdit(const QDate &date, QWidget *parent = nullptr)

              - 显示格式

                - API

                  - setDisplayFormat(format_str)

                    - 设置日期时间显示格式

                  - displayFormat() -> str

                    - 获取日期时间显示格式

                - 应用场景

                  - 设置展示的section格式

                - 案例

                  - 测试以上API

              - 最大和最小日期

                - 最大

                  - setMaximumDate(QDate)

                    - 设置最大日期
                    - 默认包含9999年12月31日

                  - maximumDate() -> QDate

                    - 获取最大日期

                  - clearMaximumDate()

                    - 清除自定义最大日期, 恢复默认

                - 最小

                  - setMinimumDate(QDate)

                    - 设置最小日期
                    - 默认1752年9月14日

                  - minimumDate() -> QDate

                    - 获取最小日期

                  - clearMinimumDate()

                    - 清除自定义最小日期, 恢复默认

                - 范围

                  - setDateRange(min_date, max_date)

              - 获取日期

                - date() -> QDate

              - ...

            - 信号

              - 继承父类

          - QTimeEdit

            - 描述

              - 基于QDateTimeEdit控件的小控件
              - 主要操作时间部分

            - 继承

              - QDateTimeEdit

            - 功能作用

              - 构造函数

                - QTimeEdit(QWidget *parent = nullptr)
                - QTimeEdit(const QTime &time, QWidget *parent = nullptr)

              - 显示格式

                - API

                  - setDisplayFormat(format_str)

                    - 设置日期时间显示格式

                  - displayFormat() -> str

                    - 获取日期时间显示格式

                - 应用场景

                  - 设置展示的section格式

                - 案例

                  - 测试以上API

              - 时间

                - 最大

                  - setMaximumTime(QTime)
                  - maximumTime() -> QTime
                  - clearMaximumTime()

                - 最小

                  - setMinimumTime(QTime)
                  - minimumTime() -> QTime
                  - clearMinimumTime()

                - 范围

                  - setTimeRange(min_time, max_time)

              - 获取时间

                - time() -> QTime

              - ...

            - 信号

              - 继承父类

    - 组合框(下拉选择输入)

      - QComboBox

        - 描述

          - 是一个组合控件
          - 默认展示最小的空间给用户操作
          - 可通过下拉选择界面, 选取更多的预置选项

        - 继承

          - QWidget

        - 功能作用

          - 构造函数

            - API

              - QComboBox(parent: QWidget = None)

            - 应用场景

              - 构造出一个空白的下拉列表控件
              - 后续通过操作数据的方法设置数据列表

            - 案例

              - 测试以上API

          - 数据操作

            - API

              - 添加条目项

                - addItem(str, userData: Any = None)
                - addItem(QIcon, str, userData: Any = None)
                - addItems(Iterable[str])

              - 插入条目项

                - insertItem(int, str, userData: Any = None)
                - insertItem(int, QIcon, str, userData: Any = None)
                - insertItems(int, Iterable[str])

              - 设置条目项

                - setItemIcon(int, QIcon)
                - setItemText(int, str)
                - setItemData(int, Any, role: int = Qt.UserRole)

              - 删除条目项

                - removeItem(int index)

              - 插分割线

                - insertSeparator(int index)

              - 设置当前编辑文本

                - setCurrentIndex(int index)
                - setCurrentText(QString text)
                - setEditText(QString text)

                  - 结合设置可被编辑

              - 了解

                - 模型操作

                  - setModel(QAbstractItemModel model)
                  - setModelColumn(int visibleColumn)
                  - setRootModelIndex(QModelIndex index)
                  - model() 
                  - modelColumn()
                  - rootModelIndex()

                - 视图操作

                  - setView(QAbstractItemView *itemView)
                  - view() 

                - 代理设置

                  - setItemDelegate(QAbstractItemDelegate *delegate)

            - 应用场景

              - 增删改条目内容

            - 案例

              - 测试以上API

          - 常用数据获取

            - API

              - count() -> int
              - itemIcon(int index) -> QIcon
              - itemText(int index) -> str
              - itemData(int index) -> Any
              - currentIndex() -> int
              - currentText() -> str

            - 应用场景

              - 获取相关数据

            - 案例

              - 测试以上API

          - 数据限制

            - API

              - setMaxCount(int max)
              - maxCount() 
              - setMaxVisibleItems(int maxItems)
              - maxVisibleItems()

            - 应用场景

              - 限制数据内容显示等限制

            - 案例

              - 测试以上API

          - 尝龟操作

            - API

              - 可编辑

                - setEditable(bool editable)
                - isEditable()

              - 可重复

                - setDuplicatesEnabled(bool enable)
                - duplicatesEnabled()

              - 有框架

                - setFrame(bool)
                - hasFrame()

              - 图标尺寸

                - setIconSize(QSize)
                - iconSize()

              - 尺寸调整策略

                - setSizeAdjustPolicy(QComboBox.SizeAdjustPolicy policy)

                  - QComboBox.AdjustToContents	

                    - 组合框将始终根据内容进行调整

                  - QComboBox.AdjustToContentsOnFirstShow

                    - 组合框将在第一次显示时调整其内容。

                  - QComboBox.AdjustToMinimumContentsLength

                    - 请改用AdjustToContents或AdjustToContentsOnFirstShow。

                  - QComboBox.AdjustToMinimumContentsLengthWithIcon

                    - 组合框将调整为minimumContentsLength加上图标的空间。出于性能原因，请在大型模型上使用此策略。

                - sizeAdjustPolicy() -> QComboBox.SizeAdjustPolicy
                - setMinimumContentsLength(int characters)
                - minimumContentsLength() -> int

              - 清空

                - clear()

                  - 移除所有项目

                - clearEditText()

                  - 清除组合框中用于编辑的行编辑内容

              - 弹出

                - showPopup()

              - 完成器

                - setCompleter(QCompleter completer)
                - completer() -> QCompleter

              - 验证器

                - setValidator(QValidator validator)
                - validator()

            - 应用场景

              - 看着用吧

            - 案例

              - 测试一下, 以后按需求来用即可!

        - 信号

          - activated(int index)

            - 某个条目被选中时

              - 必须是用户交互, 造成的值改变才会发射这个信号

          - activated(QString text)

            - 某个条目被选中时

              - 必须是用户交互, 造成的值改变才会发射这个信号

          - currentIndexChanged(int index)

            - 当前选中的索引发生改变时

              - 用户交互
              - 代码控制

          - currentIndexChanged(QString text)

            - 当前选中的索引发生改变时

              - 用户交互
              - 代码控制

          - currentTextChanged(QString text)

            - 当前的文本内容发生改变时

          - editTextChanged(QString text)

            - 编辑的文本发生改变时

          - highlighted(int index)

            - 高亮

          - highlighted(QString text)

            - 高亮

        - 案例

          - 给定城市数据

                city_dic = {
                
                    "北京": {
                
                        "东城": "001",
                
                        "西城": "002",
                
                        "朝阳": "003",
                
                        "丰台": "004"
                
                    },
                
                    "上海": {
                
                        "黄埔": "005",
                
                        "徐汇": "006",
                
                        "长宁": "007",
                
                        "静安": "008",
                
                        "松江": "009"
                
                    },
                
                    "广东": {
                
                        "广州": "010",
                
                        "深圳": "011",
                
                        "湛江": "012",
                
                        "佛山": "013"
                
                    }
                
                }

          - 实现两级联动效果

        - 相关子类

          - QFontComboBox

            - 描述

              - 组合框中填充了按字母顺序排列的字体系列名称列表
              - 让用户选择字体家族

            - 继承

              - QComboBox

            - 功能作用

              - 设置和获取当前字体

                - setCurrentFont(QFont f)
                - currentFont() -> QFont

              - 设置和获取过滤器

                - setFontFilters(QFontComboBox.FontFilters)
                - fontFilters() -> QFontComboBox.FontFilters

            - 信号

              - 继承

                - currentIndexChanged(QString text)

              - currentFontChanged(QFont font)

            - 补充

              - QFontComboBox.FontFilters

                - QFontComboBox.AllFonts

                  - 显示所有字体

                - QFontComboBox.ScalableFonts

                  - 显示可缩放字体

                - QFontComboBox.NonScalableFonts

                  - 显示不可缩放的字体

                - QFontComboBox.MonospacedFonts

                  - 显示等宽字体

                - QFontComboBox.ProportionalFonts

                  - 显示比例字体

    - 滑块(QAbstractSlider)(鼠标)

      - QSlider

        - 描述

          - 垂直或水平滑块
          - 它允许用户沿水平或垂直凹槽移动滑块手柄，并将手柄的位置转换为合法范围内的整数值

        - 继承

          - QAbstractSlider

        - 功能作用

          - 继承自父类
          - 刻度控制

            - API

              - setTickPosition(self, QSlider.TickPosition)

                - QSlider.NoTicks

                  - 0

                    - 不要画任何刻度线。

                - QSlider.TicksBothSides

                  - 3

                    - 在凹槽两侧画刻度线。

                - QSlider.TicksAbove

                  - 1

                    - 在（水平）滑块上方绘制刻度线

                - QSlider.TicksBelow

                  - 2

                    - 在（水平）滑块下方绘制刻度线

                - QSlider.TicksLeft

                  - 1

                    - 在（垂直）滑块的左侧绘制刻度线

                - QSlider.TicksRight

                  - 2

                    - 在（垂直）滑块右侧绘制刻度线

              - sd.tickPosition() -> QSlider.TickPosition
              - sd.setTickInterval(int)

                - 这是值间隔，而不是像素间隔。如果为0，滑块将在singleStep和pageStep之间进行选择

              - sd.tickInterval() -> int

            - 应用场景

              - 控制滑块刻度位置以及刻度密度

        - 信号

          - 继承自父类

        - 拓展案例

          - 要求

            - 在滑块移动时, 通过标签, 展示滑块当前数值
            - 并要求标签位置, 一直在滑块所在位置中间

          - 示例效果

            - slider-案例.gif

      - QScrollBar

        - 描述

          - 使用户能够访问比用于显示它的窗口小部件更大的文档部分
          - 一般是结合QAbstractScrollArea使用
          - 滚动条通常包括四个单独的控件：滑块，滚动箭头和页面控件

        - 继承

          - QAbstractSlider

        - 功能作用

          - 继承自父类
          - 注意, 控件尺寸需要手动调整
          - 如果想要调整滚动条长度, 参考右图

        - 信号

          - 继承自父类

      - QDial

        - 描述

          - 倒圆的范围控制
          - 比如汽车仪表盘上的速度计

        - 继承

          - QAbstractSlider

        - 功能作用

          - 继承自父类
          - 是否显示刻度

            - setNotchesVisible(bool)
            - notchesVisible() -> bool

          - 大刻度控制

            - setPageStep(int)

          - 是否启用包裹

            - setWrapping(bool)

              - 启用则会在控件周边都设置上刻度, 可以任意指向

            - wrapping() -> bool

          - 凹口之间的目标像素数

            - setNotchTarget(float)
            - notchTarget() -> float

          - 缺口大小

            - notchSize()

              - 默认值1

        - 信号

          - 继承自父类

    - 橡皮筋选中

      - QRubberBand

        - 描述

          - 提供一个矩形或线来指示选择或边界
          - 一般结合鼠标事件一同协作

        - 继承

          - QWidget

        - 功能作用

          - 构造函数

            - QRubberBand(QRubberBand.Shape, QWidget)

              - QRubberBand.Line
              - QRubberBand.Rectangle

          - 移动

            - move(x, y)
            - move(QPoint)

          - 调整大小

            - resize(width, height)
            - resize(QSize)

          - 统一设置

            - setGeometry(int x, int y, int width, int height)
            - setGeometry(QRect rect)

          - 形状获取

            - shape() -> QRubberBand.Shape

        - 信号

          - 继承父类

        - 案例

          - 在一个空白窗口内, 展示多个复选框控件
          - 通过橡皮筋实现批量选中与取消选中效果
          - 效果图

    - 对话框(QDialog)

      - QFontDialog

        - 描述

          - 提供了一种选择字体的对话框控件

        - 继承

          - QDialog

        - 功能作用

          - 构造函数

            -     QFontDialog(parent: QWidget = None)
            -     QFontDialog(QFont, parent: QWidget = None)

          - 打开对话框

            - open(self)
            - open(PYQT_SLOT)

              - 打开后, 会自动连接fontSelected信号与此处指定的槽函数

            - exec() -> int

          - 当前字体

            - setCurrentFont(QFont)
            - currentFont() -> QFont

          - 最终选中字体

            - selectedFont() -> QFont

          - 选项控制

            - setOption(QFontDialog.FontDialogOption, on=True)

              - on = True

                - 设置该选项

              - on = False

                - 取消该选项

            - setOptions(QFontDialog.FontDialogOption)

              - 设置多个选项

            - testOption(QFontDialog.FontDialogOption)

              - 测试某个选项是否生效

            - options() -> QFontDialog.FontDialogOption

              - 获取当前的选项

            - 补充

              - QFontDialog.FontDialogOption

                - QFontDialog.NoButtons

                  - 不显示“ 确定”和“ 取消”按钮。（对“实时对话框”有用。）

                - QFontDialog.DontUseNativeDialog

                  - 在Mac上使用Qt的标准字体对话框而不是Apple的原生字体面板。

                - QFontDialog.ScalableFonts

                  - 显示可缩放字体

                - QFontDialog.NonScalableFonts

                  - 显示不可缩放的字体

                - QFontDialog.MonospacedFonts

                  - 显示等宽字体

                - QFontDialog.ProportionalFonts

                  - 显示比例字体

          - 静态方法

            - getFont(parent: QWidget = None) -> Tuple[QFont, bool]
            - getFont(QFont, parent: QWidget = None, caption: str = '', options: QFontDialog.FontDialogOption) -> Tuple[QFont, bool]

              - 参数

                - 1: 默认字体
                - 2. 父控件
                - 3. 对话框标题
                - 4. 选项

              - 返回值

                - (最终字体, 是否点击确认)

        - 信号

          - currentFontChanged(QFont)

            - 当前字体发生改变时

          - fontSelected(QFont)

            - 最终选择字体时

      - QColorDialog

        - 描述

          - 颜色对话框的功能是允许用户选择颜色

        - 继承

          - QDialog

        - 功能作用

          - 构造函数

            - QColorDialog(parent: QWidget = None)
            - QColorDialog(Union[QColor, Qt.GlobalColor, QGradient], parent: QWidget = None)

          - 打开对话框

            - open(self)
            - open(PYQT_SLOT)

              - 打开后, 会自动连接colorSelected信号与此处指定的槽函数

            - exec() -> int

          - 当前颜色

            - setCurrentColor(QColor())
            - currentColor() -> QColor

          - 最终选中颜色

            - selectedColor()

          - 选项控制

            - setOption(self, QColorDialog.ColorDialogOption, on: bool = True)
            - setOptions(self, Union[QColorDialog.ColorDialogOptions, QColorDialog.ColorDialogOption])
            - testOption(self, QColorDialog_ColorDialogOption)
            - 补充

              - QColorDialog.ColorDialogOption

                - QColorDialog.ShowAlphaChannel

                  - 允许用户选择颜色的alpha分量。

                - QColorDialog.NoButtons

                  - 不显示“ 确定”和“ 取消”按钮。（对“实时对话框”有用。）

                - QColorDialog.DontUseNativeDialog

                  - 使用Qt的标准颜色对话框而不是操作系统原生颜色对话框。

          - 静态方法

            - customCount() -> int
            - setCustomColor(int index, QColor color)
            - customColor(int index) -> QColor
            - setStandardColor(int index, QColor color)
            - standardColor(int index) -> QColor
            - getColor(initial: Union[QColor, Qt.GlobalColor, QGradient] = Qt.white, parent: QWidget = None, title: str = '', options: Union[QColorDialog.ColorDialogOptions, QColorDialog.ColorDialogOption] = QColorDialog.ColorDialogOptions()) -> QColor

        - 信号

          - colorSelected(QColor color)
          - currentColorChanged(QColor color)

      - QFileDialog

        - 描述

          - 提供了一个对话框，允许用户选择文件或目录
          - 允许用户遍历文件系统，以选择一个或多个文件或目录

        - 继承

          - QDialog

        - 功能作用

          - 最简单的获取方式(静态方法)

            - 获取文件

              - getOpenFileName(parent: QWidget = None, caption: str = '', directory: str = '', filter: str = '', initialFilter: str = '', options: Union[QFileDialog.Options, QFileDialog.Option] = 0) -> Tuple[str, str]
              - getOpenFileNames(parent: QWidget = None, caption: str = '', directory: str = '', filter: str = '', initialFilter: str = '', options: Union[QFileDialog.Options, QFileDialog.Option] = 0) -> Tuple[List[str], str]
              - getOpenFileUrl(parent: QWidget = None, caption: str = '', directory: str = '', filter: str = '', initialFilter: str = '', options: Union[QFileDialog.Options, QFileDialog.Option] = 0, supportedSchemes: Iterable[str] = []) -> Tuple[QUrl, str]
              - getOpenFileUrls(parent: QWidget = None, caption: str = '', directory: str = '', filter: str = '', initialFilter: str = '', options: Union[QFileDialog.Options, QFileDialog.Option] = 0, supportedSchemes: Iterable[str] = []) -> Tuple[List[QUrl], str]
              - getSaveFileName(parent: QWidget = None, caption: str = '', directory: str = '', filter: str = '', initialFilter: str = '', options: Union[QFileDialog.Options, QFileDialog.Option] = 0) -> Tuple[str, str]
              - getSaveFileUrl(parent: QWidget = None, caption: str = '', directory: str = '', filter: str = '', initialFilter: str = '', options: Union[QFileDialog.Options, QFileDialog.Option] = 0, supportedSchemes: Iterable[str] = []) -> Tuple[QUrl, str]

            - 获取文件夹

              - getExistingDirectory(parent: QWidget = None, caption: str = '', directory: str = '', options: Union[QFileDialog.Options, QFileDialog.Option] = QFileDialog.ShowDirsOnly) -> str
              - getExistingDirectoryUrl(parent: QWidget = None, caption: str = '', directory: QUrl = QUrl(), options: Union[QFileDialog.Options, QFileDialog.Option] = QFileDialog.ShowDirsOnly, supportedSchemes: Iterable[str] = []) -> QUrl

            - 补充

              - 过滤字符串格式

                - 名称1(*.jpg *.png);;名称2(*.py)

          - 构造函数

            - QFileDialog(QWidget, Union[Qt.WindowFlags, Qt.WindowType])
            - QFileDialog(parent: QWidget = None, caption: str = '', directory: str = '', filter: str = '')

          - 接收模式

            - acceptMode() -> QFileDialog.AcceptMode
            - setAcceptMode(QFileDialog.AcceptMode)
            - 补充

              - QFileDialog.AcceptMode

                - QFileDialog.AcceptOpen

                  - 打开

                - QFileDialog.AcceptSave

                  - 保存

          - 默认后缀

            - setDefaultSuffix(str)
            - defaultSuffix() -> str

          - 设置文件模式

            - setFileMode(QFileDialog.FileMode)
            - fileMode() -> QFileDialog.FileMode
            - 补充

              - QFileDialog.FileMode

                - QFileDialog.AnyFile

                  - 文件的名称，无论是否存在。

                - QFileDialog.ExistingFile

                  - 单个现有文件的名称。

                - QFileDialog.Directory

                  - 目录的名称。显示文件和目录。但是，本机Windows文件对话框不支持在目录选择器中显示文件。

                - QFileDialog.ExistingFiles

                  - 零个或多个现有文件的名称。

          - 设置名称过滤器

            - setNameFilter(str)
            - setNameFilters(str)

          - 显示信息的详细程度

            - setViewMode(QFileDialog.ViewMode)
            - viewMode() -> QFileDialog.ViewMode
            - 补充

              - QFileDialog.ViewMode

                - QFileDialog.Detail
                - QFileDialog.List

            - 经测试, win10下不太灵光

          - 设置指定角色的标签名称

            - setLabelText(self, QFileDialog.DialogLabel, str)

              - QFileDialog.FileName
              - QFileDialog.Accept
              - QFileDialog.Reject
              - QFileDialog.FileType
              - QFileDialog.LookIn

          - 打开对话框

            - open(self)
            - open(PYQT_SLOT)

              - 打开后, 会自动连接 filesSelected 信号与此处指定的槽函数

            - exec() -> int

        - 信号

          - currentChanged(path_str)

            - 当前路径发生改变时

          - currentUrlChanged(QUrl)

            - 当前路径url发生改变时

          - directoryEntered(directory_str)

            - 打开选中文件夹时

          - directoryUrlEntered(QUrl directory)

            - 打开选中文件夹url时

          - filterSelected(filter_str)

            - 选择名称过滤器时

          - fileSelected(str)

            - 最终选择文件时

          - filesSelected([str])

            - 选择多个文件时

          - urlSelected(QUrl url)

            - 最终选择url时

          - urlsSelected(List[QUrl])

            - 最终选择多个url时

        - 作业

      - QInputDialog

        - 描述

          - 提供了一个简单方便的对话框，获得来自用户的单个值
          - 输入值可以是字符串，数字或列表中的项目
          - 设置标签以告知用户应输入的内容

        - 继承

          - QDialog

        - 功能作用

          - 常用的静态方法

            - getInt(QWidget, str, str, value: int = 0, min: int = -2147483647, max: int = 2147483647, step: int = 1, flags: Union[Qt.WindowFlags, Qt.WindowType] = Qt.WindowFlags()) -> Tuple[int, bool]
            - getDouble(QWidget, str, str, value: float = 0, min: float = -2147483647, max: float = 2147483647, decimals: int = 1, flags: Union[Qt.WindowFlags, Qt.WindowType] = Qt.WindowFlags()) -> Tuple[float, bool]
            - getDouble(QWidget, str, str, float, float, float, int, Union[Qt.WindowFlags, Qt.WindowType], float) -> Tuple[float, bool]
            - getText(QWidget, str, str, echo: QLineEdit.EchoMode = QLineEdit.Normal, text: str = '', flags: Union[Qt.WindowFlags, Qt.WindowType] = Qt.WindowFlags(), inputMethodHints: Union[Qt.InputMethodHints, Qt.InputMethodHint] = Qt.ImhNone) -> Tuple[str, bool]
            - getMultiLineText(QWidget, str, str, text: str = '', flags: Union[Qt.WindowFlags, Qt.WindowType] = Qt.WindowFlags(), inputMethodHints: Union[Qt.InputMethodHints, Qt.InputMethodHint] = Qt.ImhNone) -> Tuple[str, bool]
            - getItem(QWidget, str, str, Iterable[str], current: int = 0, editable: bool = True, flags: Union[Qt.WindowFlags, Qt.WindowType] = Qt.WindowFlags(), inputMethodHints: Union[Qt.InputMethodHints, Qt.InputMethodHint] = Qt.ImhNone) -> Tuple[str, bool]

          - 构造函数

            - QInputDialog(parent: QWidget = None, flags: Union[Qt.WindowFlags, Qt.WindowType] = Qt.WindowFlags())

          - 选项设置

            - setOption(self, QInputDialog.InputDialogOption, on: bool = True)
            - setOptions(self, Union[QInputDialog.InputDialogOptions, QInputDialog.InputDialogOption])
            - testOption(self, QInputDialog.InputDialogOption) -> bool
            - options(self) -> QInputDialog.InputDialogOptions
            - 补充

              -  QInputDialog.InputDialogOption

                 - QInputDialog.NoButtons

                   - 不显示“ 确定”和“ 取消”按钮（对“实时对话框”有用）。

                 - QInputDialog.UseListViewForComboBoxItems

                   - 使用QListView而不是不可编辑的QComboBox来显示使用setComboBoxItems（）设置的项目。

                 - QInputDialog.UsePlainTextEditForTextInput

                   - 使用QPlainTextEdit进行多行文本输入。该值在5.2中引入。

          - 输入模式

            - inputMode(self) -> QInputDialog.InputMode
            - setInputMode(self, QInputDialog.InputMode)
            - QInputDialog.InputMode

              - TextInput
              - IntInput
              - DoubleInput

          - 界面文本设置

            - setLabelText(str)

              - labelText(self) -> str

            - setOkButtonText(str)
            - setCancelButtonText(str)

          - 各个小分类设置

            - 整型

              - setIntMaximum(self, int)

                - intMaximum(self) -> int

              - setIntMinimum(self, int)

                - intMinimum(self) -> int

              - setIntRange(self, int, int)
              - setIntStep(self, int)

                - intStep(self) -> int

              - setIntValue(self, int)

                - intValue(self) -> int

            - 浮点型

              - setDoubleMaximum(self, float)

                - doubleMaximum() -> float

              - setDoubleDecimals(self, int)

                - doubleDecimals() -> int

              - setDoubleMinimum(self, float)

                - doubleMinimum(self) -> float

              - setDoubleRange(self, float, float)
              - setDoubleStep(self, float)

                - doubleStep(self) -> float

              - setDoubleValue(self, float)

                - doubleValue(self) -> float

            - 字符串

              - setTextEchoMode(self, QLineEdit.EchoMode)

                - textEchoMode(self) -> QLineEdit.EchoMode

              - setTextValue(self, str)

                - textValue(self) -> str

            - 下拉列表

              - setComboBoxItems(self, Iterable[str])

                - comboBoxItems(self) -> List[str]

              - setComboBoxEditable(self, bool)

                - isComboBoxEditable(self) -> bool

        - 信号

          - intValueChanged(int value)
          - intValueSelected(int value)
          - doubleValueChanged(double value)
          - doubleValueSelected(double value)
          - textValueChanged(text_str)
          - textValueSelected(text_str)

    - 日期

      - QCalendarWidget

        - 描述

          - 提供了一个基于每月日历控件，允许用户选择一个日期
          - 图示

        - 继承

          - QWidget

        - 功能作用

          - 构造函数

            - QCalendarWidget(parent: QWidget = None)

          - 日期范围

            - setMinimumDate(QDate date)

              - minimumDate() -> QDate

            - setMaximumDate(QDate date)

              - maximumDate() -> QDate

            - setDateRange(QDate min, QDate max)

          - 日期编辑

            - setDateEditEnabled(bool enable)

              - isDateEditEnabled() -> bool
              - 默认可以被编辑

            - setDateEditAcceptDelay(int delay)

              - dateEditAcceptDelay() -> int

            - 当控件获取焦点时, 直接输入数字, 可以快速修改日期

          - 日期获取

            - monthShown() -> int
            - yearShown() -> int
            - selectedDate() -> QDate

          - 格式外观

            - 导航条

              - isNavigationBarVisible() -> bool
              - setNavigationBarVisible(bool)

            - 一周的第一天

              - setFirstDayOfWeek(Qt.DayOfWeek dayOfWeek)

                - firstDayOfWeek() -> Qt.DayOfWeek

            - 网格显示

              - isGridVisible() -> bool
              - setGridVisible(bool)

            - 文本格式

              - setHeaderTextFormat(QTextCharFormat format)

                - headerTextFormat() -> QTextCharFormat

              - setHorizontalHeaderFormat(QCalendarWidget.HorizontalHeaderFormat format)

                - horizontalHeaderFormat() -> QCalendarWidget.HorizontalHeaderFormat
                - 补充

                  - QCalendarWidget.HorizontalHeaderFormat

                    - QCalendarWidget.SingleLetterDayNames

                      - 英文

                        - M

                      - 中文

                        - 周

                    - QCalendarWidget.ShortDayNames

                      - 英文

                        - Mon

                      - 中文

                        - 周一

                    - QCalendarWidget.LongDayNames

                      - 英文

                        - Monday

                      - 中文

                        - 星期一

                    - QCalendarWidget.NoHorizontalHeader

                      - 标题是隐藏的。

              - setVerticalHeaderFormat(QCalendarWidget.VerticalHeaderFormat format)

                - verticalHeaderFormat() -> QCalendarWidget.VerticalHeaderFormat
                - 补充

                  - QCalendarWidget.VerticalHeaderFormat

                    - QCalendarWidget.ISOWeekNumbers	

                      - 标题显示ISO周数，如QDate.weekNumber()所述。

                    - QCalendarWidget.NoVerticalHeader

                      - 标题是隐藏的。

              - setWeekdayTextFormat(self, Qt.DayOfWeek, QTextCharFormat)

                - weekdayTextFormat(Qt.DayOfWeek dayOfWeek) -> QTextCharFormat

              - setDateTextFormat(QDate date, QTextCharFormat format)

                - dateTextFormat(self, Union[QDate, datetime.date]) -> QTextCharFormat
                - dateTextFormat(self) -> object

          - 选中

            - setSelectedDate(QDate date)
            - setSelectionMode(QCalendarWidget.SelectionMode mode)

              - selectionMode() -> QCalendarWidget.SelectionMode

            - 补充

              - QCalendarWidget.SelectionMode

                - QCalendarWidget.NoSelection

                  - 日期无法选择。

                - QCalendarWidget.SingleSelection

                  - 可以选择单日期。

          - 常用的方法

            - showToday()
            - showSelectedDate()
            - showNextYear()
            - showPreviousYear()
            - showNextMonth()
            - showPreviousMonth()
            - setCurrentPage(int year, int month)

        - 信号

          - activated(QDate date)

            - 只要用户按下Return或Enter键或双击日历小部件中的日期，就会发出此信号。

          - clicked(QDate date)

            - 单击有效日期时才会发出信号

          - currentPageChanged(int year, int month)

            - 当前显示的月份更改时会发出此信号。新的一年和一个月作为参数传递。

          - selectionChanged()

            - 当前选择的日期更改时会发出此信号

              - 鼠标
              - 代码

  - 展示控件

    - QLabel

      - 描述

        - 提供了文本或图像的显示

          - 普通文本

          - 数字

          - 富文本

            - QLabel-超链接

          - 图片

          - QLabel-动画

        - 没有提供用户交互功能

      - 继承

        - QFrame

      - 功能作用

        - 构造函数

          - QLabel(parent: QWidget = None, flags: Union[Qt.WindowFlags, Qt.WindowType] = Qt.WindowFlags())
          - QLabel(str, parent: QWidget = None, flags: Union[Qt.WindowFlags, Qt.WindowType] = Qt.WindowFlags())

        - 对齐

          - alignment() -> Qt.Alignment
          - setAlignment(Qt.Alignment)

        - 缩进和边距

          - setIndent(int)

            - indent() -> int

          - setMargin(int)

            - margin() -> int

        - 文本格式

          - setTextFormat(Qt.TextFormat)
          - textFormat()

            - Qt.TextFormat

              - Qt.PlainText

                - 文本字符串被解释为纯文本字符串。

              - Qt.RichText

                - 文本字符串被解释为富文本字符串。有关富文本的定义，请参阅支持的HTML子集。

              - Qt.AutoText

                - 自动识别是否是富文本

        - 小伙伴

          - buddy() -> QWidget 
          - setBuddy(QWidget buddy)
          - 快捷键会作用在小伙伴身上

        - 内容缩放

          - hasScaledContents() -> bool
          - setScaledContents(bool)
          - 缩放内容, 适应控件大小

            - 针对于图片有效

        - 文本交互标志

          - setTextInteractionFlags(Qt.TextInteractionFlags flags)
          - textInteractionFlags() -> Qt.TextInteractionFlags
          - 补充

            - Qt.TextInteractionFlag

              - Qt.NoTextInteraction	

                - 不可能与文本进行交互。

              - Qt.TextSelectableByMouse

                - 可以使用鼠标选择文本并使用上下文菜单或标准键盘快捷键将其复制到剪贴板。

              - Qt.TextSelectableByKeyboard

                - 可以使用键盘上的光标键选择文本。显示文本光标。

              - Qt.LinksAccessibleByMouse

                - 可以使用鼠标突出显示和激活链接。

              - Qt.LinksAccessibleByKeyboard

                - 可以使用选项卡聚焦链接并使用enter激活。

              - Qt.TextEditable

                - 该文字完全可编辑。

              - Qt.TextEditorInteraction

                - 文本编辑器的默认值。
                - TextSelectableByMouse | TextSelectableByKeyboard | TextEditable

              - Qt.TextBrowserInteraction

                - QTextBrowser的默认值。
                - TextSelectableByMouse | LinksAccessibleByMouse | LinksAccessibleByKeyboard

        - 选中文本

          - setSelection(int start, int length)
          - hasSelectedText() -> bool
          - selectedText() -> str
          - selectionStart() -> int

        - 外部链接

          - openExternalLinks() -> bool
          - setOpenExternalLinks(bool open)

        - 单词换行

          - setWordWrap(bool on)
          - wordWrap() -> bool

        - 内容操作

          - 文本字符串

            - text() -> str
            - setText(QString)

          - 数值数据

            - setNum(int num)
            - setNum(double num)

          - 图形图像

            - setPicture(QPicture)

              - picture() -> QPicture 

            - setPixmap(QPixmap)

              - pixmap() -> QPixmap 

          - 动图

            - setMovie(QMovie movie)
            - movie() -> QMovie 

              - 此类用于显示没有声音的简单动画
              - 常用操作

                - setScaledSize(QSize)
                - setPaused(bool) -> void
                - setSpeed(int percentSpeed)

                  - setSpeed(200)

                    - 两倍速

                - start()
                - stop()

          - 清空

            - clear()

      - 信号

        - linkActivated(link_str)
        - linkHovered(link_str)

    - QLCDNumber

      - 描述

        - 展示LCD样式的数字
        - 它可以显示几乎任何大小的数字
        - 它可以显示十进制，十六进制，八进制或二进制数
        - 能够展示的字符

          -  0/O, 1, 2, 3, 4, 5/S, 6, 7, 8, 9/g
          -  A, B, C, D, E, F, h, H, L, o, P, r, u, U, Y
          -  : ' 空格

      - 继承

        - QFrame

      - 功能作用

        - 构造函数

          - QLCDNumber(parent: QWidget = None)
          - QLCDNumber(int, parent: QWidget = None)

            - 参数1代表展示的数值位数

        - 设置显示数值

          - display(str)
          - display(float)
          - display(int)
          - intValue() -> int
          - value() -> float

        - 位数限制

          - setDigitCount(int)
          - digitCount() -> int

        - 模式设置

          - setMode(self, QLCDNumber.Mode)
          - mode(self) -> QLCDNumber.Mode

            - QLCDNumber.Hex

              - 十六进制

            - QLCDNumber.Dec

              - 十进制

            - QLCDNumber.Oct

              - 八进制

            - QLCDNumber.Bin

              - 二进制

          - 快捷

            - setHexMode（）
            - setDecMode（）
            - setOctMode（）
            - setBinMode（）

        - 溢出

          - checkOverflow(self, float) -> bool
          - checkOverflow(self, int) -> bool

        - 分段样式

          - setSegmentStyle(self, QLCDNumber.SegmentStyle)
          - segmentStyle(self) -> QLCDNumber.SegmentStyle

            - Outline

              - 生成填充了背景颜色的凸起部分

            - Filled

              - 默认值
              - 生成填充前景色的凸起部分。

            - Flat

              - 生成填充前景色的平坦段。

      - 信号

        - overflow()

          - 数据溢出时发射

    - QProgressBar

      - 描述

        - 提供一个水平或垂直进度条
        - 进度条用于向用户提供操作进度的指示，并向他们保证应用程序仍在运行

      - 继承

        - QWidget

      - 功能作用

        - 构造函数

          - QProgressBar(self)

        - 格式设置

          - 设置范围和当前值

            - setMinimum(self, int)

              - minimum() -> int

            - setMaximum(self, int)

              - maximum() -> int

            - setRange(self, int, int)
            - setValue(self, int)
            - reset()
            - value()
            - 注意

              - 最大值和最小值如果都是0, 则进入繁忙提示

          - setFormat(self, str)

            - ％p

              - 百分比

            - ％v

              - 当前值

            - ％m

              - 总值

          - format() -> str
          - resetFormat()
          - 格式字符对齐方式

            - setAlignment(self, Union[Qt.Alignment, Qt.AlignmentFlag])

        - 文本操作

          - setTextVisible(bool)
          - text()
          - setTextDirection(QProgressBar.Direction)

            -     BottomToTop = 1
            -     TopToBottom = 0
            -     仅仅对于垂直进度条有效

        - 方向

          - setOrientation(Qt.Orientation)

            - Qt.Horizo​​ntal
            - Qt.Vertical

          - orientation() -> Qt.Orientation

        - 倒立外观

          - setInvertedAppearance(bool)

      - 信号

        - valueChanged(int)

    - 对话框(QDialog)

      - QMessageBox

        - 描述

          - 用于通知用户或请求用户的提问和接收应答一个模态对话框
          - 对话框的构成

          - 图标可以使用标准图标

            - 效果图

        - 继承

          - QDialog

        - 功能作用

          - 构造函数

            - QMessageBox(parent: QWidget = None)
            - QMessageBox(QMessageBox.Icon, str, str, buttons: Union[QMessageBox.StandardButtons, QMessageBox.StandardButton] = QMessageBox.NoButton, parent: QWidget = None, flags: Union[Qt.WindowFlags, Qt.WindowType] = Qt.Dialog|Qt.MSWindowsFixedSizeDialogHint)

          - 展示

            - exec()
            - open()

          - 内容展示

            - 对话框标题

              - setWindowTitle(str)

            - 图标

              - 标准图标

                - setIcon(QMessageBox.Icon)

              - 自定义图标

                - setIconPixmap(QPixmap)

            - 主要标题

              - setText(str)

            - 提示文本

              - setInformativeText(str)

            - 详细文本

              - setDetailedText(self, str)

            - 按钮

              - 添加按钮

                - addButton(self, QAbstractButton, QMessageBox.ButtonRole)
                - addButton(self, str, QMessageBox.ButtonRole) -> QPushButton
                - addButton(self, QMessageBox.StandardButton) -> QPushButton

              - 获取按钮

                - button(self, QMessageBox.StandardButton) -> QAbstractButton
                - buttonRole(self, QAbstractButton) -> QMessageBox.ButtonRole
                - buttons(self) -> List[QAbstractButton]

              - 默认按钮

                - setDefaultButton(self, QPushButton)
                - setDefaultButton(self, QMessageBox.StandardButton)
                - defaultButton(self) -> QPushButton

              - setEscapeButton(self, QAbstractButton)
              - setEscapeButton(self, QMessageBox.StandardButton)
              - 被点击的按钮

                - clickedButton(self) -> QAbstractButton

              - 补充

                - QMessageBox.ButtonRole

                  - InvalidRole

                    - 该按钮无效。

                  - AcceptRole

                    - 单击该按钮将使对话框被接受（例如，确定）。

                  - RejectRole

                    - 单击该按钮会导致拒绝对话框（例如取消）。

                  - DestructiveRole

                    - 单击该按钮会导致破坏性更改（例如，对于Discarding Changes）并关闭对话框。

                  - ActionRole

                    - 单击该按钮将导致更改对话框中的元素。

                  - HelpRole

                    - 可以单击该按钮以请求帮助。

                  - YesRole

                    - 按钮是一个“是”的按钮。

                  - NoRole

                    - 按钮是一个“无”按钮。

                  - ApplyRole

                    - 该按钮应用当前更改。

                  - ResetRole

                    - 该按钮将对话框的字段重置为默认值。

                - QMessageBox.StandardButton

                  - QMessageBox.Ok

                    - 使用AcceptRole定义的“确定”按钮。

                  - QMessageBox.Open

                    - 使用AcceptRole定义的“打开”按钮。

                  - QMessageBox.Save

                    - 使用AcceptRole定义的“保存”按钮。

                  - QMessageBox.Cancel

                    - 使用RejectRole定义的“取消”按钮。

                  - QMessageBox.Close

                    - 使用RejectRole定义的“关闭”按钮。

                  - QMessageBox.Discard	

                    - “丢弃”或“不保存”按钮，具体取决于使用DestructiveRole定义的平台。

                  - QMessageBox.Apply

                    - 使用ApplyRole定义的“应用”按钮。

                  - QMessageBox.Reset

                    - 使用ResetRole定义的“重置”按钮。

                  - QMessageBox.RestoreDefaults

                    - 使用ResetRole定义的“恢复默认值”按钮。

                  - QMessageBox.Help

                    - 使用HelpRole定义的“帮助”按钮。

                  - QMessageBox.SaveAll

                    - 使用AcceptRole定义的“全部保存”按钮。

                  - QMessageBox.Yes

                    - 使用YesRole定义的“是”按钮。

                  - QMessageBox.YesToAll

                    - 使用YesRole定义的“Yes to All”按钮。

                  - QMessageBox.No

                    - 使用NoRole定义的“否”按钮。

                  - QMessageBox.NoToAll

                    - 使用NoRole定义的“No to All”按钮。

                  - QMessageBox.Abort

                    - 使用RejectRole定义的“Abort”按钮。

                  - QMessageBox.Retry

                    - 使用AcceptRole定义的“重试”按钮。

                  - QMessageBox.Ignore

                    - 使用AcceptRole定义的“忽略”按钮。

                  - QMessageBox.NoButton

                    - 无效按钮。

        - 信号

      - QErrorMessage
      - QProgressDialog

### 必备专题

- 内存管理机制

  - QObject继承树

    - 所有的对象都是直接或者间接的继承自QObject
    - QObjects在一个对象树中组织他们自己

      - 当创建一个QObject时，如果使用了其他对象作为其父对象
      - 那么，它就会被添加到父对象的children()列表中

    - 当父对象被销毁时，这个QObject也会被销毁

  - QWidget

    - 扩展了父-子关系
    - 当一个控件设置了父控件

      - 会包含在父控件内部
      - 受父控件区域裁剪
      - 父控件被删除时, 子控件会自动删除

    - 场景案例

      - 一个对话框, 上面有很多操作按钮(取消, OK)

        - 按钮和对话框本身是父子控件关系

      - 我们操作的时候, 是操作的对话框控件本身, 而不是其内部的子控件(按钮)
      - 当对话框被删除时, 内部的子控件也会自动的删除

        - 非常合理

- 信号与槽机制

  - 基本概念

    - 信号(Signal)和槽(Slot)是Qt中的核心机制, 主要作用在于对象之间进行通讯
    - 信号

      - 当一个控件的状态发生改变时, 向外界发出的信息

    - 槽

      - 一个执行某些操作的函数/方法

    - 所有继承自QWidget的控件都支持"信号与槽"的机制

  - 机制描述

    - 手动操作

      - 信号

        - 槽

    - 自动操作

      - 当信号发出时, 连接的槽函数会自动执行

  - 基本使用介绍

    - 信号

      - 控件内置的一些

        - QPushButton().pressed
        - QPushButton().clicked
        - ...

      - 也可以自定义

        - pyqtSignal()

    - 槽

      - 不同控件内置额槽函数
      - 自定义的函数/方法

    - 连接方式

      - object.信号.connect(槽函数)

    - 特性

      - 一个信号可以连接多个槽函数
      - 一个信号也可以连接另外一个信号
      - 信号的参数可以是任何Python类型
      - 一个槽可以监听多个信号
      - ...

  - 高级

    - 自定义信号

      - 带参数

    - 信号的操作

      - 连接
      - 断开
      - 发射

    - 自定义槽函数

      - lamda表达式

    - 装饰器信号与槽

- 事件机制

  - 相比较于"信号与槽"机制

    - 信号与槽机制是对事件机制的高级封装
    - 事件机制更偏底层(远离用户)

  - 图解

  - 应用

    - 1. 一般情况下, 我们直接通过内置的"信号与槽"就可以解决一般通讯问题

      - QPushButton的 clicked 等信号

    - 2. 但, 有些控件并没有提供给我们想要的信号, 我们就需要自己重写具体的事件函数, 来捕获产生的事件, 做相应的处理

      - QLabel 并没有clicked信号

    - 3. 某些场景并不会把我们想要捕获的事件传递给特定函数, 而是做了其他的额外处理, 此时, 我们可以重写事件的分发函数event()

      - 例如: 想捕获用户Tab键的点击

        - 当用户点击了Tab键, 默认是切换焦点
        - 并不会把这个事件分发给keyPressEvent函数
        - 此时, 就需要我们自己重写event, 来做分发处理

    - 4. 如果想同时对多个不同的控件进行捕获Tab点击, 那么每个都重写event()函数, 也是非常麻烦的, 所以, 考虑 安装"事件过滤器"

    - 5. QApplication对象的事件过滤器, 可以拦截所有的QObject事件; 一般不怎么使用

    - 6. QApplication对象的notify()更不怎么用, 会大大降低程序性能

  - 事件的传递

    - 如果一个控件没有处理该事件, 则会自动传递给父控件进行处理
    - 事件对象具备两个特殊方法

      - accept()

        - 自己处理了这个事件, 并告诉系统不要再向上层传递

      - ignore()

        - 自己忽略了这个事件, 告诉系统, 继续往后传递去

- 位置大小

  - 控件坐标系

    - 左上角为坐标原点，向右为x轴正方向，向下为y轴正方向
    - 图示

  - 控件位置参照

    - 父控件
    - 顶层控件则参照桌面

- ...

## 09-布局管理

### 布局概念

- 布局就是指 按照某种规则将子控件摆放在父控件中

### 布局的方式

- 手动布局

  - 绝对布局

    - 直接给定具体的坐标信息和尺寸信息
    - 设置之后, 后续如果不重新设置, 则一直不变
    - 操作方法

      - move(x, y)
      - resize(width, height)

  - 重写resizeEvent(evt)

    - 在内部, 根据父控件的尺寸大小的调整, 重新计算

- 布局管理器

  - 包含了一些特定的规则

    - 横着水平排
    - 竖着垂直排
    - 网格排
    - 表单排
    - ...

  - 使用这些布局管理器进行布局, 可以快速的实现指定布局效果, 不需要手动计算位置尺寸

### 布局管理器概念

- Qt包含一个布局管理类的集合，它们被用来描述控件如何在应用程序的用户界面中呈现的
- 当可用空间发生变化时，这些布局将自动调整控件的位置和大小
- 布局管理器不是界面控件，而是界面控件的"定位策略"
- 所有QWidget类别及其子类都可以用布局来管理它们的子控件

  - 布置子控件。
  - 最高层窗口可感知的默认大小。
  - 最高层窗口可感知的最小大小。
  - 调整大小的处理。
  - 当内容改变的时候自动更新： 

    - 字体大小、文本或者子控件的其它内容。
    - 隐藏或者显示子控件。
    - 移除一些子控件。

- 布局管理器的继承图

  - QLayout

    - QBoxLayout

      - QHBoxLayout
      - QVBoxLayout

    - QGridLayout
    - QStackedLayout
    - QFormLayout

### 布局的简单使用演示

- 1. 创建布局对象

  - 不需要设置父对象
  - layout = QLayout()

- 2. 设置布局对象参数

  - margin

    - setContentsMargins(self, int, int, int, int)

  - spacing

    - setSpacing(self, int)

  - alignment

    - setAlignment(self, QWidget, Union[Qt.Alignment, Qt.AlignmentFlag]) -> bool
    - setAlignment(self, QLayout, Union[Qt.Alignment, Qt.AlignmentFlag]) -> bool
    - setAlignment(self, Union[Qt.Alignment, Qt.AlignmentFlag])

- 3. 设置给需要布局子控件的父控件\调整方向

  - QWidget.setLayout(QLayout)
  - QWidget.setLayoutDirection(Qt.RightToLeft)

    - Qt.LeftToRight	

      - 从左到右的布局。

    - Qt.RightToLeft

      - 从右到左的布局。

    - Qt.LayoutDirectionAuto

      - 自动布局。

  - QWidget.unsetLayoutDirection()

- 4. 将布局控件内部的子控件添加到布局管理器中, 自动进行布局

  - 注意, 创建子控件时, 不需要设置父控件

### 布局管理器的详细使用

- 基类

  - QLayout

    - 作用

      - 布局管理器的抽象基类

    - 功能作用

      - 小控件之间的间距

        - setSpacing(int)
        - spacing() -> int

      - 外边距

        - setContentsMargins(int left，int top，int right，int bottom)
        - 在大多数平台上，边距在所有方向上都是11像素

      - 添加子控件

        - addWidget(QWidget  w)

      - 替换子控件

        - replaceWidget（QWidget * from，QWidget * to，Qt :: FindChildOptions options = Qt :: FindChildrenRecursively）
        - 注意

          - 被替换的控件, 不再被此布局管理;

            - 隐藏
            - 删除
            - 重新添加到新的布局中

      - 添加子布局

        - addLayout(QLayout layout)

      - 能用性

        - isEnabled() -> bool
        - setEnabled(bool)

  - QBoxLayout

    - 作用

      - 提供水平或垂直方向的布局管理器
      - 这个一般很少直接用, 会选择用两个封装好的子类

    - 功能作用

      - 构造函数

        - QBoxLayout(QBoxLayout.Direction, parent: QWidget = None)

          - parent一般不写

        - QBoxLayout.Direction

          - QBoxLayout.LeftToRight

            - 从左到右水平。

          - QBoxLayout.RightToLeft

            - 从右到左水平。

          - QBoxLayout.TopToBottom

            - 从上到下垂直。

          - QBoxLayout.BottomToTop

            - 从下到上垂直。

      - 修改方向

        - setDirection(QBoxLayout_Direction)
        - direction(self) -> QBoxLayout.Direction

      - 添加元素

        - 添加控件

          - addWidget(self, QWidget, stretch: int = 0, alignment: Union[Qt.Alignment, Qt.AlignmentFlag] = Qt.Alignment())
          - insertWidget(self, int, QWidget, stretch: int = 0, alignment: Union[Qt.Alignment, Qt.AlignmentFlag] = Qt.Alignment())

        - 添加子布局

          - addLayout(self, QLayout, stretch: int = 0)
          - insertLayout(self, int, QLayout, stretch: int = 0)

        - 替换控件

          - replaceWidget(self, QWidget, QWidget, options: Union[Qt.FindChildOptions, Qt.FindChildOption] = Qt.FindChildrenRecursively) -> QLayoutItem

        - 移除控件

          - removeWidget(self, QWidget)
          - 或者
          - QWidget.hide()

            - show()会再次参与布局

        - 添加空白

          - addSpacing(self, int)
          - insertSpacing(self, int, int)

        - 添加伸缩(弹簧)

          - addStretch(self, stretch: int = 0)
          - insertStretch(self, int, stretch: int = 0)

            - stretch（int index）

      - 设置伸缩因子

        - setStretchFactor(self, QWidget, int) -> bool
        - setStretchFactor(self, QLayout, int) -> bool

      - 边距

        - setContentsMargins(self, int, int, int, int)
        - setSpacing(self, int)

          - spacing() -> int

- QHBoxLayout

  - 继承父类
  - 只是在构造函数中确定了方向为水平方向

    - 也可以改

- QVBoxLayout

  - 继承父类
  - 只是在构造函数中确定了方向为垂直方向

    - 也可以改

- QFormLayout

  - 应用场景

    - 表单样例

    - 管理输入控件及其关联标签的形式
    - 它以两列的形式列出其子元素。
    - 左列由标签组成，右列由“字段”小部件（行编辑器，旋转框等）组成。

  - 功能作用

    - 构造函数

      - QFormLayout(parent: QWidget = None)

        - parent一般不写

    - 行操作

      - 添加行

        - addRow(self, QWidget, QWidget)
        - addRow(self, QWidget, QLayout)
        - addRow(self, str, QWidget)
        - addRow(self, str, QLayout)
        - addRow(self, QWidget)
        - addRow(self, QLayout)

      - 插入行

        - insertRow(self, int, QWidget, QWidget)
        - insertRow(self, int, QWidget, QLayout)
        - insertRow(self, int, str, QWidget)
        - insertRow(self, int, str, QLayout)
        - insertRow(self, int, QWidget)
        - insertRow(self, int, QLayout)

      - 获取行信息

        - getWidgetPosition(self, QWidget) -> Tuple[int, QFormLayout.ItemRole]
        - getLayoutPosition(self, QLayout) -> Tuple[int, QFormLayout.ItemRole]
        - 行的总个数

          - rowCount() -> int

      - 修改行

        - setLayout(self, int, QFormLayout.ItemRole, QLayout)
        - setWidget(self, int, QFormLayout.ItemRole, QWidget)
        - 注意

          - 根据行号和角色, 设置相关控件或布局，如果有必要会延长布局
          - 如果单元格已被占用，则不会设置成功

      - 移除行(删除子控件)

        - removeRow(self, int)
        - removeRow(self, QWidget)
        - removeRow(self, QLayout)

      - 移除行(不删除子控件)

        - takeRow(self, int) -> QFormLayout.TakeRowResult
        - takeRow(self, QWidget) -> QFormLayout.TakeRowResult
        - takeRow(self, QLayout) -> QFormLayout.TakeRowResult

      - 标签操作

        - labelForField()

          - labelForField(self, QWidget) -> QWidget
          - labelForField(self, QLayout) -> QWidget

      - 补充

        - QFormLayout.ItemRole(角色)

          - QFormLayout.LabelRole

            - 标签

          - QFormLayout.FieldRole

            - 输入框

          - QFormLayout.SpanningRole

            - 跨越标签和输入框的控件

    - 行的包装策略

      - setRowWrapPolicy(QFormLayout.RowWrapPolicy)
      - rowWrapPolicy() -> QFormLayout.RowWrapPolicy
      - 补充

        - QFormLayout.DontWrapRows

          - 字段总是放在标签旁边。

        - QFormLayout.WrapLongRows

          - 标签被赋予足够的水平空间以适合最宽的标签，其余的空间被赋予字段。
          - 如果字段的最小大小比可用空间宽，则该字段将换行到下一行。

        - QFormLayout.WrapAllRows

          - 字段总是位于其标签下方。

    - 对齐方式

      - setFormAlignment(self, Union[Qt.Alignment, Qt.AlignmentFlag])

        - formAlignment() -> Qt.Alignment

      - setLabelAlignment(self, Union[Qt.Alignment, Qt.AlignmentFlag])

        - labelAlignment(self) -> Qt.Alignment

    - 间距

      - setVerticalSpacing(int)

        - verticalSpacing() -> int

      - setHorizo​​ntalSpacing(int)

        - horizo​​ntalSpacing() -> int

      - spacing() -> int

    - 字段增长策略

      - setFieldGrowthPolicy(QFormLayout.FieldGrowthPolicy)
      - fieldGrowthPolicy() -> QFormLayout.FieldGrowthPolicy
      - 补充

        - QFormLayout.FieldsStayAtSizeHint

          - 这些领域永远不会超出其有效大小的提示。这是QMacStyle的默认值。

        - QFormLayout.ExpandingFieldsGrow

          - 水平大小策略为Expanding或MinimumExpanding的字段将增长以填充可用空间。其他领域不会超出其有效大小提示。这是Plastique的默认政策。

        - QFormLayout.AllNonFixedFieldsGrow

          - 具有允许它们增长的大小策略的所有字段将增长以填充可用空间。这是大多数样式的默认策略。

    - 布局项操作(了解)

      - addItem(self, QLayoutItem)
      - removeItem(self, QLayoutItem)
      - itemAt(self, int, QFormLayout.ItemRole) -> QLayoutItem
      - itemAt(self, int) -> QLayoutItem
      - getItemPosition(self, int) -> Tuple[int, QFormLayout.ItemRole]
      - setItem(self, int, QFormLayout.ItemRole, QLayoutItem)

- QGridLayout

  - 应用场景

    - 网格布局
    - 取可用空间(通过其父布局或parentWidget())，将其划分为行和列
    - 并将其管理的每个窗口小控件放入正确的单元格中。
    - 每列/行具有最小宽度和拉伸系数

      - 最小宽度是使用 set XXX MinimumWidth()
      - 拉伸因子使用 set XXX Stretch()

  - 功能作用

    - 构造函数

      - QGridLayout(QWidget)
      - QGridLayout()

    - 元素操作

      - 控件

        - addWidget(self, QWidget)
        - addWidget(self, QWidget, int row, int col, alignment: Union[Qt.Alignment, Qt.AlignmentFlag] = Qt.Alignment())
        - addWidget(self, QWidget, int fromRow, int fromCol, int rowSpan, int colSpan, alignment: Union[Qt.Alignment, Qt.AlignmentFlag] = Qt.Alignment())

      - 布局

        - addLayout(self, QLayout,  int row, int col, alignment: Union[Qt.Alignment, Qt.AlignmentFlag] = Qt.Alignment())
        - addLayout(self, QLayout, int fromRow, int fromCol, int rowSpan, int colSpan, alignment: Union[Qt.Alignment, Qt.AlignmentFlag] = Qt.Alignment())

      - 获取

        - 位置获取

          - getItemPosition(self, int) -> Tuple[int, int, int, int]

        - 条目获取

          - itemAtPosition(int row，int column)

    - 列宽/行高和拉伸系数

      - setColumnMinimumWidth(int column，int minSize)

        - columnMinimumWidth(int column) -> int

      - setColumnStretch(int column，int stretch)

        - columnStretch(int column) -> int

      - setRowMinimumHeight(int row，int minSize)

        - rowMinimumHeight(int row) -> int

      - setRowStretch(int row，int stretch)

        - rowStretch(int row) -> int

    - 间距

      - setVerticalSpacing(int spacing)

        - verticalSpacing() -> int

      - setHorizontalSpacing(int spacing)

        - horizontalSpacing() -> int

      - setSpacing(int spacing)

        - spacing() -> int

    - 原点角

      - originCorner() -> Qt.Corner
      - setOriginCorner(Qt.Corner corner)
      - 补充

        - Qt.Corner

          - Qt.TopLeftCorner
          - Qt.TopRightCorner
          - Qt.BottomLeftCorner
          - Qt.BottomRightCorner

    - 信息获取

      - cellRect(int row，int column) -> QRect
      - columnCount() -> int
      - rowCount() -> int

- QStackedLayout

  - 应用场景

    - 提供一个堆叠起来的布局, 在同一时刻只能显示一个控件
    - 里面提供了相关方法, 可以切换控件

  - 功能作用

    - 构造函数

      - QStackedLayout()
      - QStackedLayout(QWidget)
      - QStackedLayout(QLayout)

    - 添加子控件

      - addWidget(self, QWidget) -> int
      - insertWidget(self, int, QWidget) -> int

    - 获取子控件

      - widget(int index) -> QWidget

    - 切换

      - setCurrentIndex(self, int)

        - currentIndex(self) -> int

      - setCurrentWidget(self, QWidget)

        - currentWidget(self) -> QWidget

    - 展示模式

      - setStackingMode(self, QStackedLayout.StackingMode)
      - stackingMode(self) -> QStackedLayout.StackingMode
      - 补充

        - QStackedLayout.StackOne

          - 只有当前小控件可见。这是默认值。

        - QStackedLayout.StackAll

          - 所有小部件都可见。当前控件显示在最前。

  - 信号

    - currentChanged（int index）
    - widgetRemoved（int index）

### 补充

- QWidget.sizeHint()

  - 合适的建议大小

    - size()的参照
    - 并不一定是最终的size()

  - 取值

    - 无布局

      - 无效值

        - isValid() 是False

    - 有布局

      - 一般是根据内容来确定, 会自动分配, 不要你管

  - 可以选择重写此方法做测试, 在后续策略验证中做测试

- QWidget.minimumSizeHint()

  - 最小的建议大小

    - minimumSize()的参照

  - 取值

    - 无布局

      - 无效值

        - isValid() 是False

    - 有布局

      - 一般是根据内容来确定, 会自动分配, 不要你管

  - layout 永远也不会把一个控件的尺寸设置到比 minimumSizeHint() 还小

    - 除非

      - 设置了最小尺寸

        - setMinimumSize()

      - or
      - 尺寸策略为Ignored

- 控件的尺寸策略

  - 作用

    - 一个控件的大小策略会告诉布局系统应该如何对它进行拉伸或收缩
    - Qt为它所有的内置控件都提供了合理的默认大小策略值
    - 一个QSizePolicy包括

      - 水平方向

        - 策略
        - 拉伸系数

      - 垂直方向

        - 策略
        - 拉伸系数

    - 注意

      - 之前讲的拉伸系数, 是在拉伸策略设置了可以被拉伸为前提

    - 策略取值

      - QSizePolicy.Fixed

        - widget 的实际尺寸只参考 sizeHint() 的返回值，不能伸展（grow）和收缩（shrink）

      - QSizePolicy.Minimum 

        - 可以伸展和收缩，不过sizeHint() 的返回值规定了 widget 能缩小到的最小尺寸

      - QSizePolicy.Maximum

        - 可以伸展和收缩，不过sizeHint() 的返回值规定了 widget 能伸展到的最大尺寸 

      - QSizePolicy.Preferred

        - 可以伸展和收缩，但没有优势去获取更大的
        - 额外空间使自己的尺寸比 sizeHint() 的返回值更大

      - QSizePolicy.Expanding 

        - 可以伸展和收缩，它会尽可能多地去获取额外的空间，也就是比 Preferred 更具优势

      - QSizePolicy.MinimumExpanding

        - 可以伸展和收缩，不过sizeHint() 的返回值规定了 widget 能缩小到的最小尺寸
        - 它比 Preferred 更具优势去获取额外空间

      - QSizePolicy.Ignored

        - 忽略sizeHint() 的作用

    - 策略图示

  - 使用方式

    - 设置控件设置尺寸策略

      - setSizePolicy(self, QSizePolicy)
      - setSizePolicy(self, QSizePolicy.Policy, QSizePolicy.Policy)

    - 补充

      - QSizePolicy

        - setHorizontalPolicy(self, QSizePolicy.Policy)
        - setHorizontalStretch(self, int)
        - setVerticalPolicy(self, QSizePolicy.Policy)
        - setVerticalStretch(self, int)
        - setRetainSizeWhenHidden(self, bool)
        - setHeightForWidth(self, bool)
        - expandingDirections(self) -> Qt.Orientations

- 尺寸约束

  - 应用场景

    - 布局对象对主控件的尺寸影响

  - 使用方式

    - QLayout.setSizeConstraint(QLayout.SizeConstraint)
    - QLayout.SizeConstraint

      - QLayout.SetDefaultConstraint

        - 主窗口最小值被设置为minimumSize()，即layout管理所需的最小尺寸，除非widget已经有最小的minimumSize尺寸。

      - QLayout.SetFixedSize

        - 主窗口的大小被设定为sizeHint()刚好适配好的大小，并不能再被重新设定大小。

      - QLayout.SetMinimumSize

        - 设定主窗口minimumSize为minimumSize()定义的，其不能再小

      - QLayout.SetMaximumSize

        - 设定主窗口的最大尺寸maxmumSize到maxmumSize()函数确定的尺寸，其不能大于这个尺寸。

      - QLayout.SetMinAndMaxSize

        - 设定主窗口的大小尺寸分别为minimumSize和maxmunSize

      - QLayout.SetNoConstraint

        - 主窗口不设定尺寸策略，保持用户设定的已有属性

## 10-样式控制

### 概念

- Qss

  - Qt Style Sheet

    - Qt 样式表

- 用来自定义控件外观的一种机制
- 可以将其类比CSS; 但没有CSS强大

  - 选择器少
  - 属性少
  - 有些属性仅适用部分控件

### 使用

- 1. 局部设置

  - 指定需要设置外观的控件, 调用该控件的setStyleSheet方法
  - widget.setStyleSheet(qss_sheet_str)
  - 参考作用范围

    - 控件本身
    - 子控件

  - 最终作用范围

    - 通过选择器二次筛选

- 2. 全局设置

  - 指定全局的QApplication对象, 调用对应的setStyleSheet方法
  - app.setStyleSheet(qss_sheet_str)
  - 参考作用范围

    - 应用程序所有控件

  - 最终作用范围

    - 通过选择器二次筛选

- 注意

  - 真实开发中, 如果对于大量qss描述, 会抽离到一个单独的.qss文件中; 到时在需要使用的地方进行读取

    - 也可以将读取操作, 封装到一个工具类中
    - 然后在需要使用的地方, 读取该字符串

### QSS语法

- 组成

  - QSS选择器

    - 作用

      - 指明哪些控件会受到样式的作用

    - 分类

      - 通配符选择器

        - * 匹配所有控件

      - 类型选择器

        - 通过控件类型来匹配控件(包含子类)

          - 控件类型

        - 例如

          - QPushButton

            - 匹配所有QPushButton或者其子类的控件实例

      - 类选择器

        - 通过控件类型来匹配控件(不包含子类)

          - .控件类型

        - 例如

          - .QPushButton

            - 只匹配所有QPushButton控件, 不包含子类

      - ID选择器

        - 通过objectName来匹配控件

          - #objectName

        - 例如

          - #hehe

            - 匹配所有objectName为hehe的控件

      - 属性选择器

        - 通过属性值来匹配控件

          - 控件类型[属性名="属性值"]

        - 例如

          - QPushButton[notice_level="warning"]

            - 匹配所有QPushButton控件
            - 并且
            - 该控件的notice_level属性值为"warning"

      - 后代选择器

        - 通过父控件(直接或者间接)子控件来筛选控件

          - 父控件 子控件

        - 例如

          - QDialog QPushButton

            - 只匹配所有QDialog中包含的QPushButton控件

              - 直接
              - 间接

      - 子选择器

        - 通过父控件的(直接)子控件来筛选控件

          - 父控件>子控件

        - 例如

          - QDialog>QPushButton

            - 只匹配所有QDialog中包含的QPushButton控件

              - 只能直接包含

      - 子控件选择器

        - 用来筛选一个复合控件上的子控件

          - 复合控件::子控件

        - 常用子控件

          - QCheckBox, QRadioButton

            - ::indicator

          - QComboBox

            - ::drop-down

          - QSpinBox, QDateEdit, QTimeEdit, QDateTimeEdit

            - ::up-button
            - ::down-button
            - ::up-arrow
            - ::down-arrow
            - 注意

              - up-button 显示在 QSpinBox 里，它的 subcontrol-origin 是相对于 QComboBox 的
              - down-button 显示在 QSpinBox 里，它的 subcontrol-origin 是相对于 QComboBox 的
              - up-arrow 显示在 up-button 里，它的 subcontrol-origin 是相对于 up-button 的
              - down-arrwo 显示在 down-button 里，它的 subcontrol-origin 是相对于 down-button 的

          - QSlider

            - ::groove
            - ::handle
            - ::add-page
            - ::sub-page
            - 注意

              - groove 显示在 QSlider 里，它的 subcontrol-origin 是相对于 QSlider 的
              - handle 显示在 groove 里，它的 subcontrol-origin 是相对于 groove 的
              - sub-page 显示在 groove 里，它的 subcontrol-origin 是相对于 groove 的
              - add-page 显示在 groove 里，它的 subcontrol-origin 是相对于 groove 的
              - handle, sub-page, add-page 虽然都显示在 groove 里，但是都可以把它们扩展到 groove 外

          - QProgressBar

            - ::chunk

          - QScrollBar

            - ::sub-line, ::add-line
            - ::sub-page, ::add-page
            - ::up-arrow, ::down-arrow
            - ::left-arrow, ::right-arrow

          - QGroupBox

            - ::title
            - ::indicator

          - QTableView

            - ::item
            - QHeaderView, QTableCornerButton 

              - ::section

          - QTreeView

            - ::item
            - ::branch
            - QHeaderView

              - ::section

          - QTabWidget

            - QTabWidget::pane
            - QTabWidget::tab-bar
            - QTabBar::tab
            - QTabBar::close-button
            - QTabBar::tear
            - QTabBar::scroller
            - QTabBar QToolButton::left-arrow
            - QTabBar QToolButton::right-arrow

      - 注意

        - 以上选择器分类可以组合使用, 使用逗号隔开即可

  - QSS伪状态

    - 作用

      - 限制控件只能在某种状态下, 被样式表作用

    - 语法

      - 选择器:伪状态

    - 例如

      - QPushButton:hover

        - 所有的QPushButton控件(或者子控件)
        - 在被鼠标经过时, 才会让后续样式表作用

    - 常见伪状态

      - :checked

        - button控件被选中

      - :unchecked

        - button控件未被选中

      - :indeterminate

        - checkBox或者radioButton被部分选中

      - :hover

        - 控件被鼠标放在上面

      - :pressed

        - 控件被按下

      - :focus

        - 控件获取焦点

      - :disabled

        - 控件失效

      - :enabled

        - 控件有效

      - :on

        - 控件处于on状态

      - :off

        - 控件处于off状态

    - 注意

      - 不同的控件可能有某种特定的伪状态, 无法通用, 具体查看官方文档
      - ! 可以否定

        - :!checked

          - 没有被选中时

      - 可以连接使用

        - :hover:checked

          - 鼠标在上and被选中时

        - :hover:!checked

          - 鼠标经过and没被选中时

  - QSS声明

    - 指明会作用怎样的样式

    - 语法

      - {  
        key: value; 
        key: value;
        }

    - 基本声明

      - 盒子模型

        - 以边框border为基准

          - margin

            - 外边距

          - padding

            - 内边距

          - content

            - 内容矩形

        - QSS控制

          - 外边距margin
          - 内边距padding

      - 边框相关(Border)

        - 边框

          - 控件的边框就是围绕控件内容和内边距的一条或多条线
          - 每个边框有 3 个方面

            - 样式
            - 宽度
            - 颜色

          - qss

            - 样式

              - 四条线统一设置

                - border-style

                  - 上 右 下 左

              - 四条线分开设置

                - border-top-style
                - border-right-style
                - border-bottom-style
                - border-left-style

              - 常用取值

                - none

                  - 定义无边框。

                - dotted

                  - 定义点状边框

                - dashed	

                  - 定义虚线

                - solid

                  - 定义实线

                - double	

                  - 定义双线

                - groove	

                  - 定义 3D 凹槽边框。其效果取决于 border-color 的值。

                - ridge

                  - 定义 3D 垄状边框。其效果取决于 border-color 的值。

                - inset

                  - 定义 3D inset 边框。其效果取决于 border-color 的值。

                - outset

                  - 定义 3D outset 边框。其效果取决于 border-color 的值。

            - 宽度

              - 四条线统一设置

                - border-width

                  - 上 右 下 左

              - 四条线分开设置

                - border-top-width
                - border-right-width
                - border-bottom-width
                - border-left-width

              - 常用取值

                - 具体的数值

                  - 10px
                  - 2em

                - 注: 一般 1em = 16px

            - 颜色

              - 四条线统一设置

                - border-color

              - 四条线分开设置

                - border-top-color
                - border-right-color
                - border-bottom-color
                - border-left-color

              - 常用取值

                - color_name

                  - red
                  - yellow
                  - green
                  - cyan
                  - ...

                - rgb_number

                  - rgb(255,0,255)

                - hex_number

                  - #00ff00

        - 边框圆角

          - 四个边框统一设置

            - border-radius

              - 圆角半径

          - 四个边框分别设置

            - border-top-left-radius
            - border-top-right-radius
            - border-bottom-right-radius
            - border-bottom-left-radius

          - 常用取值

            - 具体的像素值

        - 边框图片

          - border-image

            - url(图片路径) 四个图片裁剪值 重复

              - 裁剪值

                - 由四条线将图片裁剪为9份
                - 上

                  - 距离上边的线

                - 右

                  - 距离右边的线

                - 下

                  - 距离下边的线

                - 左

                  - 距离左边的线

              - 重复

                - 排除四个角, 其他部分的重复策略
                - round

                  - 平铺

                - repeat

                  - 重复

                - stretch

                  - 拉伸

            - border-image: url(../source/border_test.png) 30 30 30 30 repeat

          - 注意

            - 需要使用border-width辅助确定边框宽度

      - 外边距(Margin)

        - 统一设置

          - margin

            - 上 右 下 左

        - 分开设置

          - margin-top
          - margin-right
          - margin-bottom
          - margin-left

        - 常用取值

          - 16px
          - 1em

        - 注意

          - resize调整的是包含外边距的尺寸
          - 外边距变大, 边框以内尺寸会变小

      - 内边距(Padding)

        - 统一设置

          - padding

            - 上 右 下 左

        - 分开设置

          - padding-top
          - padding-right
          - padding-bottom
          - padding-left

        - 常用取值

          - 16px
          - 1em

      - 背景(Background)

        - background

          - 在一个声明中, 设置所有的背景属性
          - 组成

            - background-color
            - background-image
            - background-repeat
            - background-origin
            - background-position
            - ...

        - background-color

          - 背景颜色
          - 取值

            - 颜色

        - background-image

          - 背景图片
          - 取值

            - url(图片路径)

        - background-position

          - 对齐方式
          - 取值

            - top
            - left
            - right
            - bottom

        - background-origin

          - 位置参照
          - 取值

            - padding

              - 默认

            - content
            - border

        - background-clip

          - 背景裁剪
          - 取值

            - padding

              - 默认

            - content
            - border

        - background-repeat

          - 平铺模式
          - 取值

            - repeat-xy

              - 默认。背景图像将在垂直方向和水平方向重复。

            - repeat-x

              - 背景图像将在水平方向重复。

            - repeat-y

              - 背景图像将在垂直方向重复。

            - no-repeat

              - 背景图像将仅显示一次。

        - background-attachment

          - 是否跟随控件多余部分滚动而滚动
          - 取值

            - scroll

              - 默认值。背景图像会随着页面其余部分的滚动而移动。

            - fixed

              - 当页面的其余部分滚动时，背景图像不会移动。

      - 字体(Font)

        - 统一设置

          - font

        - 分开设置

          - font-family

            - 宋体
            - 幼圆
            - 隶书
            - ...

          - font-size

            - 16px
            - 1em

          - font-style

            - normal

              - 默认值.显示一个标准的字体样式。

            - italic

              - 显示一个斜体的字体样式。

            - oblique

              - 显示一个倾斜的字体样式。

          - font-weight

            - normal

              - 默认值。定义标准的字符。

            - bold

              - 定义粗体字符。

            - bolder

              - 定义更粗的字符。

            - lighter

              - 定义更细的字符。

            - 100
            - 200
            - 300
            - 400
            - 500
            - 600
            - 700
            - 800
            - 900

      - 文本(Text)

        - color

          - 字体颜色

      - 最大最小

        - min-width
        - min-height
        - max-width
        - max-height

      - Subcontrol

        - Subcontrol-Origin

          - 定义在 parent widget 中绘制 subcontrol 的参考矩形，默认在 padding 的矩形中绘制
          - 取值

            - margin
            - border
            - padding
            - content

        - Subcontrol-Position

          - 指明具体要在这个参考矩形的哪个位置绘制
          - 取值

            - 水平

              - left
              - center
              - right

            - 垂直

              - top
              - center
              - bottom

        - Top Bottom和 Left Right

          - position: relative;
          - position: absolute;
          - 微调 Subcontrol 的位置

        - 例如

          - QSpinBox

            QSpinBox {

                        padding-left: 10px;;
                
                        padding-right: 10px;
                
                        border:2px dotted green;
                
                        border-radius: 25px;
                
                    }
                
                    QSpinBox::up-button {
                
                        width: 50px;
                
                        height: 50px;
                
                        subcontrol-origin: padding;
                
                        subcontrol-position: left center;
                
                        left: 2px;
                
                        image: url(up.png);
                
                    }
                
                    QSpinBox::up-button:hover {
                
                        bottom: 5px;
                
                    }
                
                    QSpinBox::down-button {
                
                        width: 50px;
                
                        height: 50px;
                
                        subcontrol-origin: margin;
                
                        subcontrol-position: right center;
                
                        right: 2px;
                
                        image: url(down.png);
                
                    }
                
                    QSpinBox::down-button:hover {
                
                        top: 5px;
                
                    }

            

          - QCheckBox

                QCheckBox {
                
                    color: gray;    
                
                    border: 10px double rgb(76, 76, 76);
                
                    padding: 5px;
                
                }

             

            
            
            
            
                    QCheckBox::indicator {
                  
                        subcontrol-origin: border;
                  
                        subcontrol-position: left center;
                  
                        background: white;
                  
                        border: 2px solid gray;
            
        
        }
            
             
            


                    QCheckBox::indicator:checked {
              
                        background: rgb(76, 76, 76);
              
                    }
    
          - QComboBox
    
            QComboBox {
    
                            color: gray;
                
                            border: 6px solid lightgray;
                
                            spacing: 10px; /* indicator 和 text 的间隔 */
                
                            padding: 10px;
                
                        }


            ​             
    
                        QComboBox::drop-down {
                
                            width: 15px;
                
                            height: 10px;
                
                            subcontrol-origin: border;
                
                            subcontrol-position: bottom center;
                
                            background: white;
                
                            border: 2px dotted rgb(170, 170, 170);
                
                            border-radius: 3px;
                
                        }


            ​             
    
                        QComboBox::drop-down:hover {
                
                            background: lightgray;
                
                        }


            ​             
    
                        QComboBox::drop-down:on {
                
                            background: gray;
                
                            top: 1px;
                
                            left: 1px;
                
                        }
    
          - ...
    
    - 额外了解
    
      - 渐变色
    
        - 线性渐变
    
          - qlineargradient(x1:0, y1:0, x2:1, y2:1,stop:0 white, stop: 0.4 gray, stop:1 green)
          - 图示
    
        - 辐射渐变
    
          - qradialgradient(cx:0.7, cy:0.7, radius:0.5, fx:0.5, fy:0.5, stop:0 red,  stop:1 orange)
          - 图示
    
        - 角度渐变
    
          - qconicalgradient(cx:0.5, cy:0.5, angle:10, stop:0 red, stop:1 orange)
          - 图示
    
      - 更多属性描述
    
        - https://doc.qt.io/qt-5/stylesheet-reference.html

- 语法

  - 选择器[:伪状态] {
    声明
    }

### 注意

- 级联

  - QSS可以在QApplication、父控件、子控件中设置
  - 一个控件的最终样式, 会受到父控件和QApplication的影响

- 冲突

  - 如果一个控件, 作为后代控件, 被多个祖先控件影响

    - 则会不同属性产生叠加, 相同属性产生覆盖

  - 看特异

    - 例子1

      - QPushButton#okButton { color: gray }
      - QPushButton { color: red }

    - 例子2

      - QPushButton:hover { color: white }
      - QPushButton { color: red }

    - 例子3

      - QPushButton:enabled { color: red } 
      - QPushButton:hover { color: white } 

    - 例子4

      - QPushButton { color: red }  
      - QAbstractButton { color: gray } 

### 案例

- 常用控件效果

  - QPushButton

    - 特效

          QPushButton{
          
              color: qlineargradient(x1:0, y1:0, x2:1, y2:1,stop:0 white, stop: 0.4 red, stop:1 black);
          
              border:2px solid red;
          
              border-top-left-radius:50%;
          
              border-top-right-radius:50%;
          
              border-bottom-left-radius:10px;
          
              border-bottom-right-radius:10px
          
          }


      ​    
    
          QPushButton:hover{
          
              color: qlineargradient(x1:0, y1:0, x2:1, y2:1,stop:0 white, stop: 0.4 green, stop:1 black);
          
              border:5px dotted green;
          
              border-top-left-radius:50%;
          
              border-top-right-radius:50%;
          
              border-bottom-left-radius:10px;
          
              border-bottom-right-radius:10px
          
          }


      ​    
    
          QPushButton:pressed{
          
              font-size: 26px;
          
              border:10px double orange;
          
              border-radius: 30px; 
          
              border-top-right-radius:4px
          
          }

  - QCommandLinkButton

    - 同上
    - 修改Icon是使用

      - setIcon(QIcon) 方法

  - QRadioButton

    - 特效

      QRadioButton {

                      padding-left: 10px;
          
                      spacing: 60px;
          
                      color: red;
          
                      font-size: 20px;
          
                      border: 1px double red;
          
                      border-radius: 40px;
          
                  }
          
                  QRadioButton::indicator {         
          
                      width: 35px;
          
                      height: 30px;
          
                  }
          
                  QRadioButton::indicator::unchecked {
          
                      image: url(close_pic.png);
          
                  }
          
                  QRadioButton::indicator::checked { 
          
                      image: url(open_pic.png);
          
                  }

  - QCheckBox

    - 特效

      QCheckBox {

                      padding-left: 10px;
          
                      spacing: 60px;
          
                      color: red;
          
                      font-size: 20px;
          
                      border: 1px double red;
          
                      border-radius: 40px;
          
                  }
          
                  QCheckBox::indicator {         
          
                      width: 35px;
          
                      height: 30px;
          
                  }
          
                  QCheckBox::indicator:unchecked {
          
                      image: url(close_pic.png);
          
                  }
          
                  QCheckBox::indicator:indeterminate {
          
                      image: url(mid_pic.png);
          
                  }
          
                  QCheckBox::indicator:checked { 
          
                      image: url(open_pic.png);
          
                  }

    - 素材

  - QLineEdit

    - 特效

          QLineEdit {
          
              border: 6px solid rgb(41, 57, 85);   
          
              border-radius: 10px; 
          
              background: white;  
          
              selection-background-color: green; 
          
              font-size: 14px ;  
          
          }
          
          QLineEdit[echoMode="2"] {
          
              lineedit-password-character: 65;
          
          }
          
          QLineEdit[readOnly="true"] {
          
              background-color: gray;
          
          }
          
          QLineEdit:hover {
          
              border: 1px solid blue;  
          
          }

  - QTextEdit

    - 特效

          QTextEdit {
          
              border-radius: 20px;
          
              padding-top: 10px;
          
              padding-left: 30px;
          
              border-image: url(source/input_back.jpg);  
          
              selection-background-color: green; 
          
              font-size: 14px ;  
          
          }

  - QSpinBox

    - 特效

      QSpinBox {

                padding-left: 10px;;
          
                padding-right: 10px;
          
                border:2px dotted green;
          
                border-radius: 25px;
          
            }
          
            QSpinBox::up-button {
          
                width: 50px;
          
                height: 50px;
          
                subcontrol-origin: padding;
          
                subcontrol-position: left center;
          
                left: 2px;
          
                border-image: url(up.png);
          
            }
          
            QSpinBox::up-button:hover {
          
                bottom: 5px;
          
            }
          
            QSpinBox::down-button {
          
                width: 50px;
          
                height: 50px;
          
                subcontrol-origin: margin;
          
                subcontrol-position: right center;
          
                right: 2px;
          
                border-image: url(down.png);
          
            }
          
            QSpinBox::down-button:hover {
          
                top: 5px;
          
            }

  - QComboBox

    - 特效

          QComboBox {
          
                  color:red;
          
                  selection-background-color: orange;
          
                  min-height: 40px;
          
                  min-width: 80px;
          
          }
          
          QComboBox QAbstractItemView {
          
                  font: 14px;
          
                  selection-color: white;
          
                  selection-background-color: rgb(80, 80 80);
          
                  background-color: orange;
          
          }
          
          QComboBox QAbstractItemView::item {
          
                  color: green;
          
          }
          
          QComboBox::drop-down {
          
                  background-color: cyan;                   
          
          }
          
          QComboBox::down-arrow {
          
                  image: url(../source/down.png);
          
                  width: 20px;
          
                  height: 20px;
          
          }

  - QSlider

    - 特效

          QSlider::groove:Horizontal 
          
          {
          
              background:lightgray;
          
              height:16px;
          
              margin-left: -10px;
          
              margin-right: -10px;
          
              margin-top: -5px;
          
              margin-bottom: -5px;
          
          }
          
          QSlider::handle:Horizontal 
          
          {
          
              border-image: url(../source/hk.png);
          
              height: 60px;
          
              width:30px;
          
          }
          
          QSlider::add-page:Horizontal
          
           {     
          
              background-color: rgb(87, 97, 106);
          
              height:4px;
          
           }
          
           QSlider::sub-page:Horizontal 
          
          {
          
              background-color:qlineargradient(x1:0, y1:0, x2:1, y2:0, stop:0 cyan, stop:1 blue);
          
              height:4px;
          
           }

  - QProgressBar

    - 特效

      QProgressBar {

                  border: 2px solid gray;
          
                  border-radius: 5px;
          
                  text-align: center;
          
                  color: yellow;
          
                  font-size: 20px;
          
                  background-color: orange;
          
              }
          
              QProgressBar::chunk {
          
                  background-color: green;
          
                  width: 10px;
          
                  margin: 0.5px;
          
              }

  - ...

## 11-设计工具-QtDesigner

### 搭建GUI界面的方式

- 纯手码

  - 一行一行的通过手写代码来实现上述效果
  - 特点

    - 工作量较大
    - 新手会把代码结构搞的特别混乱

- 手码+设计工具

  - 通过可视化的设计工具，来按照所见即所得的方式进行设计界面，然后“自动转换成代码”或者直接进行使用
  - 特点

    - 直观，高效
    - 鼠标拖拖拖，点点点就可以搞定
    - 工作量小，方便修改调试
    - 界面和逻辑分离

  - 正规开发中，使用此种方式

### QtDesigner介绍

- Qt Designer中的操作方式十分灵活，其通过拖拽的方式放置控件可以随时查看控件效果

  - 并可预览效果

- Qt Designer的设计符合MVC的架构，实现了视图和逻辑的分离，从而实现了开发的便捷

  - 设计出来的用户界面能够在多种平台上使用

- Qt Designer生成的.ui文件（实质上是XML格式的文件）

  - 可以直接使用

    - from PyQt5.uic import loadUi
    - loadUi("login.ui", self)

  - 也可以通过pyuic5工具转换成.py文件

### PyQt中关于QtDesigner的使用, 和PyCharm的配置

- 辅助工具安装

  - pip install PyQt5-tools -i https://pypi.douban.com/simple

- 使用演示

  - 设计工具

    - 快速搭建一个简易的登录界面
    - 安装位置

      - \site-packages\pyqt5-tools\designer.exe

  - ui转py

    - pyuic5 $FileName$ -o ui_$FileNameWithoutExtension$.py -x
    - 安装位置

      - \Python36\Scripts\pyuic5.exe

  - qrc资源转换

    - pyrcc5 $FileName$ -o $FileNameWithoutExtension$_rc.py
    - 安装位置

      - \Python36\Scripts\pyrcc5.exe

- PyCharm外部工具配置

  - File

    - Setting

      - External Tools

### 具体使用

- 界面认识

  - 创建界面

  - 主界面

- 常用操作

  - 控件

    - 增加控件
    - 移动控件
    - 删除控件
    - 控件之间的父子关系

  - 控件属性

    - 修改
    - 新增

  - 样式表
  - 资源使用
  - 加载自定义控件(类型提升)
  - 布局操作

- 文件使用

  - .ui直接使用

    - from PyQt5.uic import loadUi
    - loadUi("login.ui", self)

  - 转成.py使用

    - 1. 根据保存的.ui文件, 生成.py文件

    - 2. 根据生成的.py文件, 创建另外一个.py文件进行加载ui

    - 3. 资源的处理

      - .qrc转换成.py

    - 4. 补全槽函数

### 注意事项

- 注意

  - 不要直接修改界面文件.py

## 补充1-自定义信号

### 1. 信号的定义

- 在类的内部, 以类属性的形式定义

  -  pyqtSignal(类型1, 类型2...)
  -  重载版本

     - pyqtSignal([int],[str]) 

- 例如

  - class Btn(QPushButton):
    doubleClick = pyqtSignal()
    doubleClick2 = pyqtSignal([int], [str])

### 2. 槽函数的定义

- 普通函数
- 方法

### 3. 信号与槽的连接

- 信号.connect(槽函数)
- 注意

  - 重载的信号选择问题

    - 信号[类型]

### 4. 信号的发射

- 信号.emit(参数1, 参数2...)
- 注意

  - 重载的信号选择问题

    - 信号[类型]

### 注意

- 一个信号连接另外一个信号时, 必须保证参数类型和个数一致

### 装饰器自动连接信号与槽

- 1. QtCore.QMetaObject.connectSlotsByName(obj)

  - 将obj内部的子孙对象的信号, 按照其objectName连接到相关的槽函数

- 2. 借助装饰器装饰固定规则的槽函数即可

  - 代码

    - @pyqtSlot()
    - def on_objectName_信号(): 
      pass

  - 等同于

    - obj.objectName.信号.connect(obj.objectName_信号)
    - def objectName_信号():
      pass

## 补充2-动画

### 功能作用

- 做一些过渡的动画效果

### 动画类别继承结构图

- QAbstractAnimation

  - QAnimationGroup

    - QParallelAnimationGroup
    - QSequentialAnimationGroup

  - QPauseAnimation
  - QVariantAnimation

    - QPropertyAnimation

### 类功能详解

- 基类功能

  - QAbstractAnimation

    - 应用场景

      - 所有动画共享的功能
      - 继承此类, 实现一些自定义动画

    - 功能作用

      - 循环操作

        - setLoopCount(int loopCount)

          - 设置动画循环次数
          - loopCount() -> int

        - currentLoop() -> int

          - 动画的当前循环
          - 从0开始

        - currentLoopTime() -> int

          - 当前循环内的时间

      - 时间操作

        - duration() -> int

          - 单次时长

        - totalDuration() -> int

          - 动画总时长

        - currentTime() -> int

          - 当前时长

      - 动画方向

        - setDirection(QAbstractAnimation.Direction)
        - direction() -> QAbstractAnimation.Direction
        - 补充

          - QAbstractAnimation.Direction

            - QAbstractAnimation.Forward

              - 动画的当前时间随着时间而增加（即，从0移动到结束/持续时间）。

            - QAbstractAnimation.Backward

              - 动画的当前时间随着时间减少（即，从结束/持续时间向0移动）。

      - 动画状态

        - state() -> QAbstractAnimation.State
        - 补充

          - QAbstractAnimation.State

            - QAbstractAnimation.Stopped
            - QAbstractAnimation.Paused
            - QAbstractAnimation.Running

    - 常用操作

      - start(QAbstractAnimation.DeletionPolicy)

        - QAbstractAnimation.DeletionPolicy

          - QAbstractAnimation.KeepWhenStopped

            - 停止时不会删除动画。

          - QAbstractAnimation.DeleteWhenStopped

            - 停止时动画将自动删除。

      - pause()
      - resume()
      - stop()
      - setCurrentTime(int)
      - setPause(bool)

    - 常用信号

      - currentLoopChanged(int currentLoop)
      - directionChanged(QAbstractAnimation.Direction newDirection)
      - finished()
      - stateChanged(QAbstractAnimation.State newState, QAbstractAnimation.State oldState)

- 子类特定功能

  - QPropertyAnimation

    - 直接父类: QVariantAnimation

      - 设置时长

        - setDuration(int msecs)

      - 开始和结束值

        - setStartValue(QVariant value)

          - startValue() -> QVariant

        - setEndValue(QVariant value)

          - endValue() -> QVariant

      - 关键值

        - setKeyValueAt(double step, QVariant value)

          - keyValueAt(double step) -> QVariant

        - setKeyValues(QVariantAnimation.KeyValues keyValues)

          - keyValues() -> QVariantAnimation.KeyValues

      - 动画曲线

        - setEasingCurve(self, Union[QEasingCurve, QEasingCurve.Type])

          - easingCurve() -> Union[QEasingCurve, QEasingCurve.Type]

        - 取值

          - https://doc.qt.io/qt-5/qeasingcurve.html#Type-enum

    - 应用场景

      - 属性动画
      - 用于实现某个属性值从x到y的动画变化

    - 功能作用

      - 1. 构造动画对象并设置目标属性

        - 方式1

          - QPropertyAnimation(parent: QObject = None)
          - setTargetObject(self, QObject)

            - targetObject(self)

          - setPropertyName(self, Union[QByteArray, bytes, bytearray])

            - propertyName(self) -> QByteArray

        - 方式2

          - QPropertyAnimation(QObject, Union[QByteArray, bytes, bytearray], parent: QObject = None)

        - 常用属性

          - geometry
          - pos
          - size
          - windowOpacity

      - 2. 设置开始值和结束值

        - setStartValue(self, Any)
        - setEndValue(self, Any)
        - setKeyValueAt(self, float, Any)
        - setKeyValues(self, object)

      - 3. 设置动画时长

        - setDuration(int mesc)

      - 4. 设置动画曲线

        - setEasingCurve(self, Union[QEasingCurve, QEasingCurve.Type])
        - 取值

          - https://doc.qt.io/qt-5/qeasingcurve.html#Type-enum

      - 5. 启动动画

        - start()

  - QPauseAnimation

    - 暂停动画, 在串行动画中使用
    - setDuration(int msecs)

      - 设置暂停时长

- 动画组

  - 应用场景

    - 可以将一组动画, 同时播放或者按顺序播放

  - 基类共性功能

    - QAnimationGroup

      - 添加动画

        - addAnimation(QAbstractAnimation animation)
        - insertAnimation(int index, QAbstractAnimation animation)

      - 移除动画

        - removeAnimation(QAbstractAnimation animation)

      - 获取动画

        - animationAt(int index) -> QAbstractAnimation

      - 获取并移除

        - takeAnimation(int index) -> QAbstractAnimation

      - 动画个数

        - animationCount() -> int

      - 清空动画

        - clear()

  - 子类功能

    - 并行动画

      - QParallelAnimationGroup

        - 功能参照父类
        - 只是添加的所有动画, 都是同时执行

    - 串行动画

      - QSequentialAnimationGroup

        - 功能参照父类

          - 只是添加的所有动画, 都是串行顺序执行

        - 子类特性功能

          - addPause(int msecs) -> QPauseAnimation
          - insertPause(int index, int msecs) -> QPauseAnimation
          - currentAnimation() -> QAbstractAnimation

        - 信号

          - currentAnimationChanged(QAbstractAnimation current)

## 阶段综合案例

### 案例效果图

- 效果.gif

### 案例功能

- 注册界面

  - 控件创建
  - 布局管理
  - 样式控制
  - 菜单动画
  - 对外接口

    - 退出按钮点击
    - 注册按钮点击

      - 账号信息
      - 密码信息

    - 弹出
    - 消失

- 登录界面

  - 控件创建
  - 布局管理
  - 样式控制
  - 菜单动画
  - 加QQ群链接生成

    - http://qun.qq.com/join.html

  - 对外接口

    - 注册账号按钮点击
    - 登录按钮点击

      - 账号信息
      - 密码信息

    - 弹出
    - 消失

- 计算器

  - 控件创建
  - 布局管理
  - 样式控制
  - 业务逻辑实现

- 界面之间的业务对接和数据传递

## 打包可执行文件

### 打包的意义

- 将 "代码+资源+依赖+环境"  打包成一个单独的文件(夹)
- 直接交付给没有安装任何环境的用户进行使用

### 常用的打包工具

- py2exe
- Cx_Freeze
- PyInstaller

### PyInstaller

- 功能作用

  - 将Python应用程序及其所有依赖项捆绑到一个包中
  - 用户无需安装Python解释器或任何模块即可运行打包的应用程序

- 平台支持

  - PyInstaller针对Windows，Mac OS X和Linux进行了测试
  - 但是，它不是交叉编译器

    - 制作Windows应用程序，在Windows中运行PyInstaller 
    - 制作一个Linux应用程序，你可以在Linux等中运行它

- 安装

  - Python版本

    - Python 3.6.3

  - pip版本

    - pip-18.1

  - 安装命令

    - pip install pyinstaller
    - 测试版本

      - 3.3.1

    - 安装位置

      - C:\Python\Python36\Scripts

  - 成功测试

    - pyinstaller --version

- 使用

  - 常用形式

    - pyinstaller [opts] main.py
    - 参数

      - -F

        - 打包成一个exe文件

      - -D
        - 创建一个目录, 包含exe文件, 会有很多依赖
        - 默认

      - -c

        - 使用控制台

      - -w

        - 使用窗口

# PyQt5 视频小计

## GUI样式设置

给项目文件统一设置字体样式`QObject.qss` ![image-20201012195035304](https://i.loli.net/2020/10/12/tOV7YTfHQwZJ4M2.png)

- ```python
  //QObject.qss 为同目录下创建的格式文件，
  with open("QObject.qss", "r") as f:
  	qApp.setStyleSheet(f.read())
  ```
  
- 匹配的`QObject.qss` 

  ```css
  QLabel{
  	font-size: 20px; color:red;
  }
  ```

- 匹配了不同`ID`的`QObject.qss`,搭配`label.setObjectName("notice")`即可实现不同`ID`的对应 
```css
  QLabel#notice{
  	font-size: 20px; color:red;
}
  ```
- ![](https://gitee.com/zr001/writeimges/raw/master/img/20201014204603.png)
![](https://gitee.com/zr001/writeimges/raw/master/img/20201014204719.png)
- 

