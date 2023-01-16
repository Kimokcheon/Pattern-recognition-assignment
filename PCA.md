# 数学理论
## 特征值分解与SVD分解 
### SVD
Every matrix $\mathbf{A} \in \mathbb{R}^{m \times n}$ has an SVD . The decomposition goes as follows:
$$
\mathbf{A}=\mathbf{U} \mathbf{\Sigma} \mathbf{V}^{\top}
$$
where $\mathbf{U} \in \mathbb{R}^{m \times m}$ and $\mathbf{V} \in \mathbb{R}^{n \times n}$ are orthogonal matrices and $\boldsymbol{\Sigma} \in \mathbb{R}^{m \times n}$ is a diagonal matrix with the singular values of $\mathbf{A}$ (denoted $\sigma_{i}$ ) on its diagonal.
# 应用场景
降维就是一种对高维度特征数据预处理方法。降维是将高维度的数据保留下最重要的一些特征，去除噪声和不重要的特征，从而实现提升数据处理速度的目的。在实际的生产和应用中，降维在一定的信息损失范围内，可以为我们节省大量的时间和成本。降维也成为应用非常广泛的数据预处理方法。
# 解决思路 
## 结合方式 
### Principal Component Analysis
PCA(Principal Component Analysis)，即主成分分析方法，是一种使用最广泛的数据降维算法。PCA的主要思想是将n维特征映射到k维上，这k维是全新的正交特征也被称为主成分，是在原有n维特征的基础上重新构造出来的k维特征。
## 实施方案
### 基于特征值分解协方差矩阵实现PCA算法
输入：数据集 $X=\left\{x_{1}, x_{2}, x_{3}, \ldots, x_{n}\right\}$ ，需要降到 $\mathrm{k}$ 维。
1) 去平均值(即去中心化)，即每一位特征减去各自的平均值。
2) 计算协方差矩阵 $\frac{1}{n} X X^{T}$, 注：这里除或不除样本数量 $n$ 或 $n-1$,其实对求出的特征向量没有影 响。
3) 用特征值分解方法求协方差矩阵 $\frac{1}{n} X X^{T}$ 的特征值与特征向量。
4) 对特征值从大到小排序，选择其中最大的 $k$ 个。然后将其对应的 $k$ 个特征向量分别作为行向量组 成特征向量矩阵 $P$ 。
5) 将数据转换到k个特征向量构建的新空间中，即 $\mathrm{Y}=\mathrm{PX}$ .
#### 基于SVD分解协方差矩阵实现PCA算法 
输入：数据集 $X=\left\{x_{1}, x_{2}, x_{3}, \ldots, x_{n}\right\}$ ，需要降到k维。
1) 去平均值，即每一位特征减去各自的平均值。
2) 计算协方差矩阵。
3) 通过SVD计算协方差矩阵的特征值与特征向量。
4) 对特征值从大到小排序，选择其中最大的 $\mathrm{k}$ 个。然后将其对应的 $\mathrm{k}$ 个特征向量分别作为列向量组 成特征向量矩阵。
5) 将数据转换到k个特征向量构建的新空间中。
# 总结
特征分解是SVD的一种情况。XXT是求左奇异矩阵，对数据按行降维。XTX是求右奇异矩阵，对数据按列降维。利用相关方法可以有效提取出数据特征，便于后续模型形成
# Reference
- 周志华《机器学习》
- 张学工《模式识别》
- 李航《统计学习方法》
