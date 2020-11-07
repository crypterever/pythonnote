---
title: anaconda管理环境
top: false
cover: false
toc: true
mathjax: true
date: 2020-07-31 17:56:26
tags:
 - python
 - windows
 - anaconda
password:
summary: 记录一些有关怎么创建anaconda环境和开启指定环境的命令
categories: python

---

# 查看anaconda版本信息

- ```conda --version``` ：查看版本信息。

# 升级相关

- `conda upgrade --all`：升级所有工具包。
- `conda update conda`：检查更新当前`conda`。

# 管理虚拟环境

- 使用`anaconda`可以为我们创建所需要的特定的虚拟环境。
- `conda create --name env_name python=xxx`：创建你所需要的`python虚拟环境`。
- `激活环境`
  - Windows：`activate env_name`：切换到所创建的`python虚拟环境`。
  - Mac/Linux：`source activate env_name  `。

- `conda env list`或`conda info -e`：查看所有的环境。

- `conda remove --name env_name --all`：删除一个已有的`python虚拟环境`。
- `conda remove --name $your_env_name $package_name`：不进入任何的虚拟环境，指定要删除的哪个环境的哪个包。

- `deactivate env_name  `：退出环境。

- `conda env export > environment.yml`：分享环境，会在当前工作目录下生成一个。environment.yml文件，拿到environment.yml文件后，将该文件放在工作目录下，可以通过命令`conda env create -f environment.yml`从该文件创建环境。

# conda常用命令

- `conda list`：查看安装了哪些包。
- `conda install package_name(包名)`：安装指定包。

# 使用`Qtconsole`

- 直接运行`jupyter qtconsole`（需要首先`pip install jupyter`）。

# 使用`jupyter notebook`

- 在任意文件夹中打开`cmd`：输入`jupyter notebook`，好处是生成的`ipynb`文件会保存在当前的文件夹中。
- 启动之后会打开一个网页

# 使用`jupyterlab `

- `Jupyter Lab` 的启用 和 `Jupyter Notebook` 方法一样，只需要将输入的 `jupyter notebook` 换成 `jupyter lab` 即可。
- 我们点击 `jupyterlab` 下面的 `Launch` ，会在默认浏览器（我这里是 Chrome）打开 *http://localhost:8888/lab* 这样一个东东，这里就可以输入 Python 代码啦，来一句 Hello World 吧。

> 友情链接：[CSDN](https://blog.csdn.net/ITLearnHall/article/details/81708148)

# 彻底卸载anaconda

- 打开`anaconda prompt`：
  - 输入```conda install anaconda-clean```
- 输入```anaconda-clean --yes```
- 通过`Uninstall-Anaconda3.exe`

# 急救方法

- `终端`用命令`anaconda-navigator`运行`anaconda`