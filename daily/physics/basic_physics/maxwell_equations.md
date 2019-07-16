# 麦克斯韦方程组

  * 描述电场和磁场的方程。

----
## 基本变量


## 基础方程

### 洛伦兹力
#### 表达式
$$\vec{F} = q (\vec{E} + \vec{v} \times \vec{B})$$
其中，$\vec{E}$表示电场，$\vec{B}$表示磁场，q是带电粒子的电荷量，v是带电粒子的速度。

#### 积分形式
$$F = \int_V (\rho \vec{E} + \vec{J} \times \vec{B}) d\tau$$
其中，V是积分的体积，$\rho$是电荷密度，J是电流密度，$d\tau$是微小体元素。

#### 单位体积的洛伦兹力
即，洛伦兹力密度$\vec{f}$
$$\vec{f} = \rho \vec{E} + \rho \vec{v} \times \vec{B} =  \rho \vec{E} + \vec{J} \times \vec{B}$$

### 库仑定律
两个电荷之间的库仑力。
$$\vec{F} = \frac{1}{4 \pi \epsilon_0} \frac{Q_1 Q_2}{r^2} \vec{r}$$
其中，Q是电荷，r是电荷之间的距离，$\vec{r}$是表示方向的单位向量。

### 毕奥-萨伐尔定律
适用于计算一个稳定电流所产生的磁场。
$$\vec{B}(\vec{r}) = \frac{\mu_0 I}{4 \pi}\int_{L'} dl' \times \frac{\vec{r} - \vec{r}'}{|\vec{r} - \vec{r}'|^3}$$

## 麦克斯韦方程组
这里$\vec{E}$表示电场，$\vec{B}$表示磁场，$\mu_0$和$\epsilon_0 $为常数。  
积分形式中Q是电荷，I是电流，V表示一块体积，$\partial V$表示其表面积，而S表示一块曲面，$\partial S$表示其边缘。  
微分形式中$\rho$是电荷密度（电荷/体积），$\vec{J}$是电流密度（电流/面积），$\nabla \cdot$和$\nabla \times$是两个不同的算符，基本可以理解为对向量的某种微分。

### 积分形式
  * (1) $$\oint_{\partial V} \vec{E} \cdot d \vec{a} = \frac{Q_V}{\epsilon_0}$$
  * (2) $$\oint_{\partial S} \vec{E} \cdot d \vec{l} = - \frac{d}{dt} \int_S \vec{B} \cdot d \vec{a}$$
  * (3) $$\oint_{\partial V} \vec{B} \cdot d \vec{a} = 0$$
  * (4) $$\oint_{\partial S} \vec{B} \cdot d \vec{l} = \mu_0 I_s + \mu_0 \epsilon_0 \frac{d}{dt} \int_S \vec{E} \cdot d \vec{a}$$

### 微分形式
  * (1) $$\nabla \cdot \vec{E} = \frac{\rho}{\epsilon_0}$$
  * (2) $$\nabla \times \vec{E} = - \frac{\partial}{\partial t} \vec{B}$$
  * (3) $$\nabla \cdot \vec{B} = 0$$
  * (4) $$\nabla \times \vec{B} = - \mu_0 \vec{J} + \mu_0 \epsilon_0 \frac{\partial}{\partial t} \vec{E}$$