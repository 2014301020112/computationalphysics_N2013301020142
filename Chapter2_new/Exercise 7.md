#第二章 第19题 Level 1-2  
姓名：吴雨桥  
学号：2013301020142  
日期：2016年4月10日  
## 摘要  
在本文中，我讨论了阻尼系数和轴方向不同的自旋对棒球轨迹的影响，证明了适当加入自旋后棒球的轨迹会变得难以预测。
## 背景介绍  
![](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter2_new/%E6%A3%92%E7%90%83%E8%BF%90%E5%8A%A8%E7%A4%BA%E6%84%8F.gif)  
本文中主要讨论棒球运动中受到打击的棒球的运动规律。为了研究棒球的实际运动，我们必须要考虑两种不同的物理效应。其中一种效应是棒球的自旋；它对曲线球的运动轨迹有决定性的影响。另一种效应考虑到了棒球的质地（粗糙或光滑）对阻尼系数（drag coefficient）的影响，所谓“knuckleball”的运动轨迹与这第二种效应有关。  
## 不同质地的棒球的阻尼系数  
在《计算物理》一书的33页的图2.6中作者给出了对于不同质地的棒球，阻尼系数关于运动速度的函数关系。该图是一个经验图像，为了将之应用于后文中的计算中去，我在此对于每一种质地（光滑、普通、粗糙）的棒球的阻尼系数定义一个分段函数，使得分段函数的图像与经验图像尽可能相似。  
[![](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter2_new/drag%20appr.png)](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter2_new/drag%20coefficient%20define.py)  
点击图片可以获得绘图的源代码。这幅图与书中所给的经验图相比做了相当的简化，但是保留了转折点的值以及函数变化趋势。  
为了直观看到不同质地的棒球阻尼系数不同带来的轨迹的不同，我做了一个简单的模拟。以110mph(30.56m/s)的初速度，45°的角度，1m的挥棒高度将这三种不同的球击打出去，观察它们的运动轨迹。  
[![](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter2_new/drag%20ball.png)](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter2_new/drag%20ball.py)  
点击图片以获得绘图源代码。  
[![](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter2_new/3d%20drag%20co.gif)](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter2_new/3d%20drag%20coe.py)  
点击动图以获得绘图的源代码。  
从上方的静态图和动态图中，我们可以发现由于阻尼系数的函数关系比较复杂，棒球的质地会对球的轨迹有很复杂的影响。由此，棒球的运动轨迹才可能变化多端。   
## 加入自旋后棒球的运动方程  
棒球的自旋会使得空气对棒球产生一种力，流体力学中称为马格努斯力。  
![](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter2_new/%E9%A9%AC%E6%A0%BC%E5%8A%AA%E6%96%AF%E5%8A%9B%E7%A4%BA%E6%84%8F%E5%9B%BE.jpg)   
理论推导表明，马格努斯力的大小与棒球自转的角速度、棒球的半径和棒球在空气中的运动速度有关。以S0表示空气对棒球的牵引力的平均效应，可得棒球所受马格努斯力的表达式为  
![](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter2_new/%E9%A9%AC%E6%A0%BC%E5%8A%AA%E6%96%AF%E5%8A%9B%E5%85%AC%E5%BC%8F.png)  
注意到此处的表达式是标量式，当我们将其应用到三维空间中时，我们应当使用矢量表达式。由此，同时考虑到了上文中提到的阻尼系数的函数关系，我们可以得到三维空间中的棒球运动方程。  
![](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter2_new/equation.png)   
在这个方程组中D是上文中的阻尼系数，S0/m=0.00041是一个经验常数。  
## 不同的自旋对棒球的影响
在下文中，为了突出自旋的作用，我将暂时只考虑一个normal的棒球。同时我将不引入风速。  
首先是以45°，110mph击打出的normal ball在自旋轴垂直于地面的不同自旋下的运动轨迹。  
[![](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter2_new/sb1.png)](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter2_new/z%20omega.py)  
点击图片以获得绘图源代码。两张图的横坐标均为击打的方向，第一张图的纵坐标是垂直地面方向，第二张图的纵坐标是击打方向的与地面平行的垂直方向。  
[![](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter2_new/spin%203d%20vertical.gif)](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter2_new/spin%203d%20vertical.py)  
点击动图以获得绘制的源代码。由图可以看出，由于自旋的效应，球的轨迹可以变得非常特别。同时球偏转的方向与马格努斯力的理论相符。红色、橙色、黄色、绿色和蓝色的棒球分别代表角速度0,100rps,500rps,1000rps和2000rps。
然后我们看一下同样的棒球在平行于地面，垂直于击打方向的自旋下的轨迹。  
[![](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter2_new/sb2.png)](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter2_new/z%20omega%20-%20Copy.py)  
点击图片以获得绘图的源代码。可以看出x-y平面上轨迹变得奇异，而x-z平面上基本没什么变化。  
[![](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter2_new/%E8%8B%A5%E6%B0%B4GIF%E6%88%AA%E5%9B%BE_2016%E5%B9%B44%E6%9C%8819%E6%97%A523%E7%82%B96%E5%88%8650%E7%A7%92.gif)](https://raw.githubusercontent.com/wuyuqiao/computationalphysics_N2013301020142/master/Chapter2_new/spin%203d%20vertical%20-%20Copy.py)  
点击动图以获得绘图的源代码。从这张动图中可以看到，棒球在垂直方向上的运动轨迹变得变化多端。红色、橙色、黄色、绿色和蓝色的棒球分别代表角速度0,100rps,500rps,1000rps和2000rps。  
##结论  
自旋对于棒球轨迹有决定性的影响，如果在击打和投掷棒球时加上自旋，可以使得轨迹难以预测。
