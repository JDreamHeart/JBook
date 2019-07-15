# 麦克斯韦方程组

  * 描述电场和磁场的方程。

----

## 方程组
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