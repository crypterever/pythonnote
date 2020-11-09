# Python机器学习

> **机器学习路线图**：![路线图](https://gitee.com/zr001/writeimges/raw/master/img/%E6%9C%AA%E5%91%BD%E5%90%8D%E7%BB%98%E5%9B%BE.png)
>
> **机器学习开发流程图**：![开发流程图](https://gitee.com/zr001/writeimges/raw/master/img/%E5%BC%80%E5%8F%91%E6%B5%81%E7%A8%8B%E5%9B%BE.png)
>
> 认识：![image-20201108090626475](https://gitee.com/zr001/writeimges/raw/master/img/image-20201108090626475.png) `机器学习`小白版：![image-20201108103358290](https://gitee.com/zr001/writeimges/raw/master/img/image-20201108103358290.png)

# [SKlearn](https://scikit-learn.org/stable/)

## **SKlearn**简介

scikit-learn，又写作sklearn，是一个开源的基于`python`语言的机器学习工具包。它通过`NumPy`, `SciPy`和`Matplotlib`等`python`数值计算的库实现高效的算法应用，并且涵盖了几乎所有主流机器学习算法。

 `SKlearn`官网链接：http://scikit-learn.org/stable/index.html

 在工程应用中，用`python`手写代码来从头实现一个算法的可能性非常低，这样不仅耗时耗力，还不一定能够写出构架清晰，稳定性强的模型。更多情况下，是分析采集到的数据，根据数据特征选择适合的算法，在工具包中调用算法，调整算法的参数，获取需要的信息，从而实现算法效率和效果之间的平衡。而`sklearn`，正是这样一个可以帮助我们高效实现算法应用的工具包。

 `sklearn`有一个完整而丰富的官网，里面讲解了基于`sklearn`对所有算法的实现和简单应用。

> `scikit-learn` 算法选择：
>
> 流程图隐含条件：
>
> - <font color=#6495ED>蓝色圆圈</font>：判断条件
> - <font color=#00FF7F>绿色圆圈</font>：可供选择的算法

 ![英文版](https://scikit-learn.org/stable/_static/ml_map.png)

 ![中文版](https://gitee.com/zr001/writeimges/raw/master/img/image-20201108092241737.png)

## 常用模块

`sklearn`中常用的模块有分类、回归、聚类、降维、模型选择、预处理。

![image-20201108092936473](https://gitee.com/zr001/writeimges/raw/master/img/image-20201108092936473.png)

`分类`：识别某个对象属于哪个类别，常用的算法有：SVM（支持向量机）、nearest neighbors（最近邻）、random forest（随机森林），常见的应用有：垃圾邮件识别、图像识别。

`回归`：预测与对象相关联的连续值属性，常见的算法有：SVR（支持向量机）、 ridge regression（岭回归）、Lasso，常见的应用有：药物反应，预测股价。

`聚类`：将相似对象自动分组，常用的算法有：k-Means、 spectral clustering、mean-shift，常见的应用有：客户细分，分组实验结果。

`降维`：减少要考虑的随机变量的数量，常见的算法有：PCA（主成分分析）、feature selection（特征选择）、non-negative matrix factorization（非负矩阵分解），常见的应用有：可视化，提高效率。

`模型选择`：比较，验证，选择参数和模型，常用的模块有：grid search（网格搜索）、cross validation（交叉验证）、 metrics（度量）。它的目标是通过参数调整提高精度。

`预处理`：特征提取和归一化，常用的模块有：preprocessing，feature extraction，常见的应用有：把输入数据（如文本）转换为机器学习算法可用的数据。

## 安装SKlearn

- `scikit-learn`需要：
  - Python
  - Numpy
  - Scipy

- 安装时可以直接运行： 

```python
pip install -U scikit-learn
```

- 其他命令：

  - 更新`pip`：

    - ```python
      python -m pip install --upgrade pip
      ```

  - 安装`scipy`：

    - 在网址http://www.lfd.uci.edu/~gohlke/pythonlibs/ 中找到你需要的版本scipy

      例如windows 64 位 Python2.7 对应下载:scipy-0.18.0-cp27-cp27m-win_amd64.whl

      cd 下载scipy 目录下，安装

      ```python
      pip install scipy-0.18.0-cp27-cp27m-win_amd64.whl
      ```

  - 安装`matplotlib`：

    - ```python
      pip install matplotlib
      ```

  - 安装`numpy+mkl`：

    - 在网址http://www.lfd.uci.edu/~gohlke/pythonlibs/ 找到你需要的numpy+mkl版本

      然后 cd 到numpy+mkl所在的目录下，安装

      ```python
      pip install  numpy-1.11.1+mkl-cp27-cp27m-win_amd64.whl 
      # 不同Python版本安装版本随之改变
      pip install -U scikit-learn
      ```

- 要升级或卸载scikit-learn安装了python或者`conda`你**不应该使用PIP命令**。
  - `conda`：
    - 升级`scikit-learn`：`conda update scikit-learn`

    - 卸载`scikit-learn`：`conda remove scikit-learn`

  - `Python`：
    - 使用`pip install -U scikit-learn`安装或者使用`pip uninstall scikit-learn`卸载可能都没有办法更改有conda命令安装的sklearn。

## 官方文档中文版学习笔记：

>  [官方文档中文版](https://apachecn.gitee.io/sklearn-doc-zh/)

## 监督学习：

> ![image-20201108103719325](https://gitee.com/zr001/writeimges/raw/master/img/image-20201108103719325.png)

### 1.1广义线性模型：

官网实例（翻译）：

`Linear Regression Example`：

本例仅使用糖尿病数据集的第一个特征，以说明这种回归技术的二维图。在图中可以看到直线，显示了线性回归如何试图画出一条直线，使数据集中观察到的反应与线性近似预测的反应之间的残差平方和最小化。

还计算了系数、残差平方和和确定系数。

`Out`:

![image-20201108172152611](https://gitee.com/zr001/writeimges/raw/master/img/image-20201108172152611.png)

```markdown
Coefficients:
 [938.23786125]
Mean squared error: 2548.07 //均方差
Coefficient of determination: 0.47
```

```python
print(__doc__)


# Code source: Jaques Grobler
# License: BSD 3 clause


import matplotlib.pyplot as plt
import numpy as np
from sklearn import datasets, linear_model
from sklearn.metrics import mean_squared_error, r2_score

# Load the diabetes dataset
# 加载糖尿病数据集
diabetes_X, diabetes_y = datasets.load_diabetes(return_X_y=True)

# Use only one feature
# 仅使用一个特征
diabetes_X = diabetes_X[:, np.newaxis, 2]

# Split the data into training/testing sets
diabetes_X_train = diabetes_X[:-20]
diabetes_X_test = diabetes_X[-20:]

# Split the targets into training/testing sets
diabetes_y_train = diabetes_y[:-20]
diabetes_y_test = diabetes_y[-20:]

# Create linear regression object
regr = linear_model.LinearRegression()

# Train the model using the training sets
regr.fit(diabetes_X_train, diabetes_y_train)

# Make predictions using the testing set
diabetes_y_pred = regr.predict(diabetes_X_test)

# The coefficients
print('Coefficients: \n', regr.coef_)
# The mean squared error
print('Mean squared error: %.2f'
      % mean_squared_error(diabetes_y_test, diabetes_y_pred))
# The coefficient of determination: 1 is perfect prediction
print('Coefficient of determination: %.2f'
      % r2_score(diabetes_y_test, diabetes_y_pred))

# Plot outputs
# 绘图输出
plt.scatter(diabetes_X_test, diabetes_y_test,  color='black')
plt.plot(diabetes_X_test, diabetes_y_pred, color='blue', linewidth=3)

plt.xticks(())
plt.yticks(())

plt.show()
```



## 无监督学习：

> ![image-20201108103636628](https://gitee.com/zr001/writeimges/raw/master/img/image-20201108103636628.png)![image-20201108103922998](https://gitee.com/zr001/writeimges/raw/master/img/image-20201108103922998.png)

# 数学知识积累

## [经验贴](https://zhuanlan.zhihu.com/p/25197792)

### 线性代数

#### 1-1、标量

一个标量就是一个单独的数，一般用小写的变量名称表示。

#### 1-2、向量

一个向量就是一列数，这些数是有序排列的。用过次序中的索引，我们可以确定每个单独的数。通常会赋予向量粗体的小写名称。当我们需要明确表示向量中的元素时，我们会将元素排列成一个方括号包围的纵柱：![image-20201109193619958](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109193619958.png)

我们可以把向量看作空间中的点，每个元素是不同的坐标轴上的坐标。

#### 1-3、矩阵

矩阵是二维数组，其中的每一个元素被两个索引而非一个所确定。我们通常会赋予矩阵粗体的大写变量名称，比如A。 如果一个实数矩阵高度为m，宽度为n，那么我们说
$$
A\epsilon R^{m*n}
$$
![image-20201109195916741](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109195916741.png)

矩阵这东西在机器学习中就不要太重要了！实际上，如果我们现在有N个用户的数据，每条数据含有M个特征，那其实它对应的就是一个NM的矩阵呀；再比如，一张图由16x16的像素点组成，那这就是一个16x16的矩阵了。现在才发现，我们大一学的矩阵原理原来这么的有用！要是当时老师讲课的时候先普及一下，也不至于很多同学学矩阵的时候觉得莫名其妙了。

#### 1-4、张量

几何代数中定义的张量是基于向量和矩阵的推广，通俗一点理解的话，我们可以将标量视为零阶张量，矢量视为一阶张量，那么矩阵就是二阶张量。

例如，可以将任意一张彩色图片表示成一个三阶张量，三个维度分别是图片的高度、宽度和色彩数据。将这张图用张量表示出来，就是最下方的那张表格：

![image-20201109200618732](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109200618732.png)

其中表的横轴表示图片的宽度值，这里只截取0~319；表的纵轴表示图片的高度值，这里只截取0~4；表格中每个方格代表一个像素点，比如第一行第一列的表格数据为[1.0,1.0,1.0]，代表的就是RGB三原色在图片的这个位置的取值情况（即R=1.0，G=1.0，B=1.0）。

当然我们还可以将这一定义继续扩展，即：我们可以用四阶张量表示一个包含多张图片的数据集，这四个维度分别是：图片在数据集中的编号，图片高度、宽度，以及色彩数据。

张量在深度学习中是一个很重要的概念，因为它是一个深度学习框架中的一个核心组件，后续的所有运算和优化算法几乎都是基于张量进行的。

#### 1-5、范数

有时我们需要衡量一个向量的大小。在机器学习中，我们经常使用被称为范数(`norm`) 的函数衡量矩阵大小。`Lp` 范数如下：![image-20201109201440374](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109201440374.png)

所以：

![image-20201109201501416](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109201501416.png)

这里先说明一下，在机器学习中，L1范数和L2范数很常见，主要用在损失函数中起到一个限制模型参数复杂度的作用，至于为什么要限制模型的复杂度，这又涉及到机器学习中常见的过拟合问题。具体的概念在后续文章中会有详细的说明和推导，大家先记住：这个东西很重要，实际中经常会涉及到，面试中也常会被问到！！！

#### 1-6、特征分解

![image-20201109201650022](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109201650022.png)

#### 1-7、奇异值分解（Singular Value Decomposition，SVD）

![image-20201109202744869](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109202744869.png)

#### 1-8、Moore-Penrose伪逆

![image-20201109202818756](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109202818756.png)

#### 1-9、几种常用的距离

![image-20201109203035988](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109203035988.png)

##### 1、曼哈顿距离

![image-20201109203106226](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109203106226.png)

```python
from numpy import *
vector1 = mat([1,2,3])
vector2 = mat([4,5,6])
print sum(abs(vector1-vector2))
```

##### 2、欧氏距离

![](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109203254754.png)

```python
from numpy import *
vector1 = mat([1,2,3])
vector2 = mat([4,5,6])
print sqrt((vector1-vector2)*(vector1-vector2).T)
```

##### 3、闵可夫斯基距离

![image-20201109204218838](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109204218838.png)

##### 4、切比雪夫距离

![image-20201109204250549](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109204250549.png)

```python
from numpy import *
vector1 = mat([1,2,3])
vector2 = mat([4,5,6])
print sqrt(abs(vector1-vector2).max)
```

##### 5、夹角余弦

![image-20201109205357680](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109205357680.png)

```python
from numpy import *
vector1 = mat([1,2,3])
vector2 = mat([4,5,6])
print dot(vector1,vector2)/(linalg.norm(vector1)*linalg.norm(vector2))
```

##### 6、汉明距离

![image-20201109205501094](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109205501094.png)

```python
from numpy import *
matV = mat([1,1,1,1],[1,0,0,1])
smstr = nonzero(matV[0]-matV[1])
print smstr
```

##### 7、杰卡德相似系数

![image-20201109205610523](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109205610523.png)

##### 8、杰卡德距离

![image-20201109205854905](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109205854905.png)

```python
from numpy import *
import scipy.spatial.distance as dist
matV = mat([1,1,1,1],[1,0,0,1])
print dist.pdist(matV,'jaccard')
```

### 概率

#### 3-1、使用概率的原因

![image-20201109210342674](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109210342674.png)

#### 3-2、随机变量

![image-20201109210523150](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109210523150.png)

#### 3-3、概率分布

![image-20201109210610192](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109210610192.png)

#### 3-4、条件概率

![image-20201109210642625](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109210642625.png)

#### 3-5、贝叶斯公式

![image-20201109211217115](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109211217115.png)

期望、方差、协方差等主要反映数据的统计特征，机器学习的一个很大应用就是数据挖掘等，因此这些基本的统计概念也是很有必要掌握。另外，像后面的EM算法中，就需要用到期望的相关概念和性质。

#### 3-6、期望

![image-20201109212258020](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109212258020.png)

#### 3-7、方差

![image-20201109212314823](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109212314823.png)

#### 3- 8、协方差

![image-20201109212335780](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109212335780.png)

#### 3-9、常见分布函数

##### 1.	0-1分布

0-1分布是单个二值型离散随机变量的分布，其概率分布函数为：

![image-20201109212532407](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109212532407.png)

##### 2.	几何分布

![image-20201109212611001](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109212611001.png)

##### 3.	二项分布

![image-20201109212646249](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109212646249.png)

##### 4.	高斯分布

![image-20201109212711776](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109212711776.png)

##### 5.	指数分布

![image-20201109212903435](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109212903435.png)

##### 6.泊松分布

![image-20201109213152457](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109213152457.png)

#### 3-10、Lagrange乘子法

![image-20201109214940563](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109214940563.png)

#### 3-11、最大似然估计

![image-20201109215111878](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109215111878.png)

### 信息论

信息论本来是通信中的概念，但是其核心思想“熵”在机器学习中也得到了广泛的应用。比如决策树模型ID3，C4.5中是利用**信息增益**来划分特征而生成一颗决策树的，而信息增益就是基于这里所说的**熵**。所以它的重要性也是可想而知。

#### 4-1、熵

![image-20201109215308657](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109215308657.png)

#### 4-2、联合熵

![image-20201109215336679](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109215336679.png)

#### 4-3、条件熵

![image-20201109215502406](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109215502406.png)

#### 4-4、相对熵

![image-20201109215538240](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109215538240.png)

#### 4-5、互信息

![image-20201109215602775](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109215602775.png)

#### 4-6、最大熵模型

![image-20201109215632776](https://gitee.com/zr001/writeimges/raw/master/img/image-20201109215632776.png)

## 回归（Regression）

> 回归问题是针对于连续型变量的。

**举个栗子：预测房屋价格**

假设想要预测房屋价格，绘制了下面这样的数据集。水平轴上，不同房屋的尺寸是平方英尺，在竖直轴上，是不同房子的价格，单位时（千万$）。给定数据，假设一个人有一栋房子，750平方英尺，他要卖掉这栋房子，想知道能卖多少钱。

这个时候，监督学习中的回归算法就能派上用场了，我们可以根据数据集来画直线或者二阶函数等来拟合数据。

![image-20201108102406507](https://gitee.com/zr001/writeimges/raw/master/img/image-20201108102406507.png)

 通过图像，我们可以看出直线拟合出来的150k,曲线拟合出来是200k,所以要不断训练学习，找到最合适的模型得到拟合数据（房价）。

**回归通俗一点就是，对已经存在的点（训练数据）进行分析，拟合出适当的函数模型y=f(x)，这里y就是数据的标签，而对于一个新的自变量x，通过这个函数模型得到标签y。** 

## 分类(Classification)

> 和回归最大的区别在于，分类是针对离散型的，输出的结果是有限的。

**举个栗子：估计肿瘤性质**

假设某人发现了一个乳腺瘤，在乳腺上有个z肿块，恶性瘤是危险的、有害的；良性瘤是无害的。

假设在数据集中，水平轴是瘤的尺寸，竖直轴是1或0，也可以是Y或N。在已知肿瘤样例中，恶性的标为1，良性的标为0。那么，如下，蓝色的样例便是良性的，红色的是恶性的。

![image-20201108103127696](https://gitee.com/zr001/writeimges/raw/master/img/image-20201108103127696.png)

这个时候，机器学习的任务就是估计该肿瘤的性质，是恶性的还是良性的。

那么分类就派上了用场，在这个例子中就是向模型输入人的各种数据的训练样本（这里是肿瘤的尺寸，当然现实生活里会用更多的数据，如年龄等），产生“输入一个人的数据，判断是否患有癌症”的结果，结果必定是离散的，只有“是”或“否”。

所以简单来说分类就是，要通过分析输入的特征向量，对于一个新的向量得到其标签。

## 数学中一个字母上面的^符号

> `y`的估计——————（`统计学`）

# 词汇积累

- `cheat-sheet`：![image-20201108092424534](https://gitee.com/zr001/writeimges/raw/master/img/image-20201108092424534.png)

- 

