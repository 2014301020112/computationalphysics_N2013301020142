# 第十次作业 3.26、3.29、3.33及其3D展示 
姓名：吴雨桥  
学号：2013301020142  
时间：2016年4月27日  
## 摘要  
本文使用Euler法通过数值计算研究了Lorenz模型和台球问题，并回答了书上的3.26、3.29和3.33题，并使用Vpython进行了3D展示。  
## Lorenz模型  
![](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter3-3/Lorenz_Attractor.gif)  
大气物理学家Lorenz在研究Rayleigh-Benard问题时，将流体力学基本方程组Navier-Stokes方程组化简为简单形式：
![](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter3-3/Lorenz%20equations.png)  
这个方程组被称为Lorenz方程组，或Lorenz模型。其中x,y,z为变量，其余为常数。  
## Lorentz模型在不同r下的行为
接下来我们考察Lorenz模型的行为。我们令sigma=10，b=8/3，改变r的大小，观察z随时间的变化情况（x与y将呈现相似的行为）。在这个模型中，r代表了流体顶部与底部的温度差，类似于单摆问题中外界驱动力的地位。  
[![](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter3-3/z%20versus%20time%20for%20different%20r.png)](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter3-3/z%20vs%20t.py)  
点击图片以获取绘图的源代码。由图可知，当r=5时，图像一开始有一点振荡，随后振幅衰减，z变成一个与时间无关的常数。当r=10时，图像的特征相似，只是振幅衰减所花的时间要更长一些。这两种情况对应于流体中的稳定对流运动。它类似于非混沌单摆的运动模式。当r=25时，图像最终变为混沌状态。从非混沌到混沌状态的转变点为r=470/19，其推导过程在给老师的邮件中。  
## 相空间中的混沌lorenz模型  
接下来我们考察在相空间中z与x的关系。为此我们在x-z平面作图。各参数的选择与上文相同。
首先我们令r=5、10以使得系统处于非混沌状态。  
[![](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter3-3/nonchaotic.png)](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter3-3/Phase%20space%20nonchaotic.py)  
点击图片以获取绘图的源代码。有图可知，当系统处于非混沌状态时，其轨迹最终会收缩到相空间中的一个点，即代表系统处于稳定状态。
之后我们令r=25以使得系统处于混沌状态。  
[![](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter3-3/lorenz%202d.png)](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter3-3/Phase%20space.py)  
点击图片以获取绘图的源代码。由图可知，与混沌摆的情况类似，出现了奇异吸引子。由于它们出现在Lorenz模型中，习惯上被称为Lorenz吸引子。  
[![](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter3-3/Phase%203d.png)](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter3-3/phase%203d.py)  
点击图片以获取绘图的源代码。这是Lorenz吸引子的三维图示。  
[![](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter3-3/%E8%8B%A5%E6%B0%B4GIF%E6%88%AA%E5%9B%BE_2016%E5%B9%B44%E6%9C%8829%E6%97%A514%E7%82%B915%E5%88%8645%E7%A7%92.gif)](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter3-3/Phase%20space%20-%20Copy.py)  
点击图片以获取绘图的源代码。图中为Lorenz吸引子在三维相空间中形成的动态图示。
[![](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter3-3/slice1.png)](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter3-3/slice1.py)  
点击图片以获取绘图的源代码。上图为r=25时Lorentz吸引子的截面图。左图为x=0时y-z平面，右图为y=0时x-z平面。