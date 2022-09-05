#### 文章目录
- [1.自信息与熵](#1)  
    - [1.1 自信息](#1.1)
    - [1.2 熵](#1.2)
    - [1.3 相对熵(KL散度)](#1.3)
    - [1.4 JS散度](#1.4)
    - [1.5 交叉熵](#1.5)
- [2. 联合自信息与联合熵](#2)
    - [2.1 联合自信息](#2.1)
    - [2.2 联合熵](#2.1)
- [3. 条件自信息与条件熵](#3)
    - [3.1 条件自信息](#3.1)
    - [3.2 条件熵](#3.2)
- [4. 互信息](#4)
    - [4.1 互信息](#4.1)
    - [4.2 平均互信息](#4.2)
    - [4.3 KL散度与平均互信息](#4.3)
- [5. 关系总结](#5)
![关系总结](https://github.com/Catalyst0307/Pictures/blob/main/84442ad5932a4f919b6f2811eef9465d.png "关系总结") 

# <span id="1">1. 自信息与熵</span>
## <span id="1.1">1.1 自信息</span>
概率论中，随机事件是样本空间的子集。利用信息论可以对事件所包含的信息进行量化，得到信息量。事件所包含的不确定性越高，所含的信息量越大。  
假设![](https://latex.codecogs.com/svg.image?P(x_i))表示事件![](https://latex.codecogs.com/svg.image?x_i)发生的概率, ![](https://latex.codecogs.com/svg.image?I(x_i))表示事件![](https://latex.codecogs.com/svg.image?x_i)包含的信息量，则![](https://latex.codecogs.com/svg.image?I(x_i))与![](https://latex.codecogs.com/svg.image?P(x_i))的关系反映如下规律：  
1. ![](https://latex.codecogs.com/svg.image?I(x_i))与为![](https://latex.codecogs.com/svg.image?P(x_i))函数关系。即  

![](https://latex.codecogs.com/svg.image?I(x_i)=f[p(x_i)])  
    
2. ![](https://latex.codecogs.com/svg.image?P(x_i))与![](https://latex.codecogs.com/svg.image?I(x_i))为负相关关系。  
 
3. 若干相互独立事件所含信息量为各独立事件信息量的和, 即:  

![](https://latex.codecogs.com/svg.image?I(x_ix_2x_3\cdots)=I(x_1)&plus;I(x_2)&plus;I(x_3)&plus;\cdots&space;)  
      
为满足上述规律，定义事件![](https://latex.codecogs.com/svg.image?X=x_i)的**信息量或自信息**为概率的负对数:  

![](https://latex.codecogs.com/svg.image?I(x_i)=-\textrm{log}_2p(x_i))  
    
- 信息量的单位为比特(bit), 1bit对应![](https://latex.codecogs.com/svg.image?p(x_i)=\frac{1}{2})。每一个二进制码的信息量为1bit。对数的底数决定信息量单位，当底数为 _e_ 时单位为奈特(nit); 当底数为10时单位为哈特莱(Hartly)。  
  - 自信息的含义有两种：（1）当事件发生前，事件的不确定性；（2）事件发生后，事件所包含的信息量。  

- 除此之外，自信息还可描述`惊奇程度`  


## <span id="1.2">1.2 熵</span>
如果离散随机变量 ___X___ 的分布规律为：  

![](https://github.com/Catalyst0307/Pictures/blob/main/CodeCogsEqn%20(1).svg)  

则可求得随机变量 ___X___ 的平均信息量：  

![](https://latex.codecogs.com/svg.image?H(X)&space;=&space;-\sum_{i=1}^{n}p(x_i)\textrm{log}p(x_i))  

称为随机变量 ___X___ 的**信息熵**。自信息用单个事件的结果计算。而熵对整个概率分布中的平均不确定性进行量化，是从平均意义上表征随随机变量的、总体特征的一个量。换言之，一个分布的熵指 从这个分布的随机变量所能产生的期望信息总和。
- 当 ___X___ 的各个取值都是等概率 &thinsp;  ![](https://latex.codecogs.com/svg.image?\frac{1}{n}) &thinsp;  时，不确定性最大，即熵为最大值：  
![](https://latex.codecogs.com/svg.image?H_{max}&space;=&space;\textrm{log}_2n)  
- 对于二值随机变量 ___X___ ![](https://latex.codecogs.com/svg.image?\in&space;) {0,1}，有![](https://latex.codecogs.com/svg.image?p(X&space;=&space;1)&space;=&space;\theta)，![](https://latex.codecogs.com/svg.image?p(X&space;=&space;0)&space;=&space;1&space;-&space;\theta)，其熵为：  
![](https://latex.codecogs.com/svg.image?H(X)&space;=&space;-\left&space;[&space;p(X=1)\textrm{log}_2p(X=1)&plus;(X=0)\textrm{log}_2(X=0)&space;\right&space;]&space;&space;&space;&space;&space;&space;)  ![](https://latex.codecogs.com/svg.image?=&space;-&space;[\theta&space;\textrm{log}_2&space;\theta&space;&plus;(1-\theta)\textrm{log}_2(1-\theta)])  
这被称为二熵值函数(Binary Entropy Function)。  
可视化为：   
![](https://github.com/Catalyst0307/Pictures/blob/main/e1e898d7804b4c6d8897683aef7f2531.png)  


## <span id="1.3">1.3 相对熵(KL散度)</span>
**相对熵或KL散度(Kullback-Leibler Divergence)** 是一种测量同一随机变量的不同概率分布(同一概率空间的不同概率测度)差异 &ensp; 的方法。若 _p_ 和 _q_ 为随机变量 __X__ 的两个概率分布，定义 _p_ 相对于 _q_ 的相对熵为：  
![](https://latex.codecogs.com/svg.image?D_{KL}(p||q)=\sum_{1=1}^{n}p(x_i)log\frac{p(x_i)}{q(x_i)})  
由经典不等式 &emsp; ln _x_ < _x_ - 1 &emsp; 得：  
![](https://latex.codecogs.com/svg.image?\textrm{log}_2x<(\textrm{log}_2e)(x-1))  
![](https://github.com/Catalyst0307/Pictures/blob/main/CodeCogsEqn.svg)  
仅当对所有![](https://latex.codecogs.com/svg.image?x_i), ![](https://latex.codecogs.com/svg.image?p(x_i)=q(x_i))时，等式成立。上式称为散度不等式，该式说明，一个概率分布相对于另一个概率分布的散度是非负的，仅当两分布相同时，散度为0。  
> 散度并不是通常意义下的距离，如不满足对称性：![](https://latex.codecogs.com/svg.image?D_{KL}(p||q)\neq&space;D_{KL}(q||p))


## <span id="1.4">1.4 JS散度</span>、
**JS散度(Jensen–Shannon Divergence)** 是一种对称的衡量两个分布相似度的度量方式，定义为：  
![](https://github.com/Catalyst0307/Pictures/blob/main/CodeCogsEqn%20(2).svg)  
> JS散度的缺陷：当两个分布完全不重叠时，即便两分布中心距离很近，JS散度仍为常数(log2)。  


## <span id="1.5">1.5 交叉熵</span>
相对熵可拆解为：  
![](https://latex.codecogs.com/svg.image?\begin{align*}&space;D_{KL}(p||q)&=\sum_{i=1}^{n}p(x_i)\textrm{log}\frac{p(x_i)}{q(x_i)}&space;\\&space;&=\sum_{i=1}^{n}p(x_i)\textrm{log}p(x_i)-\sum_{i=1}^{n}q(x_i)\textrm{log}q(x_i)&space;\\&space;&=&space;H(p)&plus;H(q)\end{align*})  
若 _p_ 的分是已知的，则 _H(p)_ 为一个常数。此时：  
![](https://latex.codecogs.com/svg.image?argmin_qD_{KL}(p||q)) &emsp; 等价于&emsp; ![](https://latex.codecogs.com/svg.image?argmin_qH(p,q))  
所以优化计算时可将 _H(p)_ 省略，剩余的 _H(p,q)_ 就称为 **交叉熵(cross-entropy)** :  
![](https://latex.codecogs.com/svg.image?H(p,q)=&space;-\sum_{i=1}^{n}p(x_i)\textrm{log}q(x_i))


# <span id="2">2. 联合自信息与联合熵</span>
## <span id="2.1">2.1 联合自信息</span>
二维离散型随机变量的联合分布为：  
![](https://github.com/Catalyst0307/Pictures/blob/main/CodeCogsEqn%20(3).svg)   
与独立自信息类似，联合自信息  
![](https://latex.codecogs.com/svg.image?I(x_iy_j)=-\textrm{log}_2p(x_iy_j))  
当两事件相互独立时，联合自信息为两事件自信息之和：  
![](https://latex.codecogs.com/svg.image?I(x_iy_j)=I(x_i)&plus;I(y_j))


## <span id="2.2">2.2 联合熵</span>
**联合熵(Joint Entropy)** 定义为联合分布 _XY_ 上的每个元素对&ensp;![](https://latex.codecogs.com/svg.image?x_iy_j)&ensp;的数学期望，用 _H(XY)_ 或 _H(X,Y)_ 表示。  
![](https://latex.codecogs.com/svg.image?H(XY)=-\sum_{i=1}^{m}\sum_{j=1}^{n}p(x_iy_j)\textrm{log}p(x_iy_j))


# <span id="3">3. 条件自信息与条件熵</span>
## <span id="3.1">3.1 条件自信息</span>
已知&ensp;![](https://latex.codecogs.com/svg.image?y_j)&ensp;的条件下，发生&ensp;![](https://latex.codecogs.com/svg.image?x_i)&ensp;的不确定性或信息量：  
![](https://latex.codecogs.com/svg.image?I(x_i|y_j)=&space;-\textrm{log}_2p(x_i|y_j))  
同样，  
![](https://latex.codecogs.com/svg.image?I(y_j|x_i)=&space;-\textrm{log}_2p(y_j|x_i))


## <span id="3.2">3.2 条件熵</span>
两离散变量 _X_ 和 _Y_ 的样本空间组成的概率矩阵为  
![](https://github.com/Catalyst0307/Pictures/blob/main/CodeCogsEqn%20(4).svg) &emsp; 则  
1. 事件和随机变量的**条件熵(Conditional Entropy)**：  
![](https://latex.codecogs.com/svg.image?H(X|y_i)=-\sum_{i=1}^{m}p(x_i|y_j)\textrm{log}p(x_i|y_j))  
2. 随机事件和随机事件的条件熵：  
![](https://latex.codecogs.com/svg.image?H(X|Y)=-\sum_{i=1}^{m}\sum_{j=1}^{n}p(y_j)p(x_i|y_j)\textrm{log}p(x_i|y_j)&space;=-\sum_{i=1}^{m}\sum_{j=1}^{n}p(x_iy_j)\textrm{log}p(x_i|y_j))  
> ![](https://latex.codecogs.com/svg.image?H(X|Y))是![](https://latex.codecogs.com/svg.image?H(X|y_j))在 _Y_ 样本空间中的数学期望；也可看作联合自信息![](https://latex.codecogs.com/svg.image?I(x_i|y_j))在 _X_ 和 _Y_ 的联合样本空间中的数学期望。


# <span id="4">4. 互信息</span>
## <span id="4.1">4.1 互信息</span>
对于两个离散随机事件集 _X_ 和 _Y_   ，事件&ensp;![](https://latex.codecogs.com/svg.image?y_j)&ensp;的出现后关于&ensp;![](https://latex.codecogs.com/svg.image?x_i)&ensp;的信息量，定义为事件&ensp;![](https://latex.codecogs.com/svg.image?x_i)&ensp;和&ensp;![](https://latex.codecogs.com/svg.image?y_j)&ensp;的**互信息(Mutual Information)**，用&ensp;![](https://latex.codecogs.com/svg.image?I(x_i;y_j))&ensp;表示。  
![](https://latex.codecogs.com/svg.image?I(x_i;y_j)=I(x_i)-I(x_i|y_j)=\textrm{log}_2\frac{p(x_i|y_j)}{x_i})  
表示：1.已知事件&ensp;![](https://latex.codecogs.com/svg.image?y_j)&ensp;后所消除的关于事件&ensp;![](https://latex.codecogs.com/svg.image?x_i)&ensp;的不确定性；2. 事件&ensp;![](https://latex.codecogs.com/svg.image?y_j)&ensp;出现给出现关于事件&ensp;![](https://latex.codecogs.com/svg.image?x_i)&ensp;的信息量。  
互信息具有对称性：  
![](https://github.com/Catalyst0307/Pictures/blob/main/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE(146).png)


## <span id="4.2">4.2 平均互信息</span>


## <span id="4.3">4.3 KL散度与平均互信息</span>


# <span id="5">5. 关系总结</span>
