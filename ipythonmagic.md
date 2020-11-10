# Ipython中的魔法命令

**IPython**中的魔法命令有很多魔法命令，能让我们更好的使用**IPython**，同时这魔法命令也能在`JupyterNotebook`中使用，因为后者是以前者为内核的。

| 命令                  | 说明                                             |
| --------------------- | ------------------------------------------------ |
| %quickref             | 快速导引                                         |
| %magic                | Magic Functions 详细说明                         |
| %fun?                 | 获取具体帮助                                     |
| %lsmagic              | 列出所有可⽤用 Magic Functions                   |
| obj?, obj??           | 获取对象信息，?? 返回更详细的信息，⽐比如源码    |
| ?obj.*abc*            | 返回对象匹配的成员，⽐比如: str.is*              |
| !, !!                 | 执⾏行系统命令，捕获输出结果为字符串或列表       |
| %doctest_mode         | 切换 shell 提示示样式，包括提示示符、输出等设置  |
| %pprint               | Pretty-Print 开关                                |
| %bookmark             | 目录书签                                         |
| %cd, %pwd, _dh        | 工作目录                                         |
| %dirs, %popd, %pushd  | 目录栈                                           |
| %ed, %edit            | 使用编辑器打开文件                               |
| %debug                | 进入最后一次异常场景，[pdb.pm](http://pdb.pm/)() |
| %pdb                  | pdb开关，出现异常时是否进入调试模式              |
| %pdoc                 | 查看对象文档                                     |
| %psource              | 查看对象源码                                     |
| %pyfile               | 查看包含指定对象的文件内容                       |
| %pycat                | 按页查看文件                                     |
| %run                  | 运行指定文件                                     |
| %prun, %time, %timeit | 测试代码运行时间                                 |
| %psearch              | 在当前名字空间按通配符搜索名字                   |
| %who,%whos            | 查看所有变量                                     |
| %env                  | 输出环境变量                                     |
| %hist                 | 查看历史变量                                     |
| %reset                | 重置环境，移除所有名字                           |

`备注`：

> - %%表示多行模式，%仅指单行模式；
> - 在 shell command 中可以用 \$ name 引用 Python 变量名字，\$$name 引用环境变量；
> - 系统命名捕获可以直接赋值给某个名字，如 name = !unam；
> - %ed: -n 跳转到指定行；-x 退出编辑器时不执行；-p 使⽤用上一次 `ed` 命令；
> - %run: -n 设定 **name** 为⾮非 “**main**”；-i 引⼊入交互环境名字空间；-d 进⼊入调试模式。