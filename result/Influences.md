﻿# 一、影响无人机拍摄的因素

## 1.天气因素  
<div style="text-indent:2em">
<p>由于无人机体积小、重量轻，在航拍时受气流、风力、风向影响较大。当风速多大，会造成飞机飞行速度和姿态变化过大，导致照片扭曲程度过大，最终成像模糊，同时加速飞机动能消耗，导致缩短飞行时间。天对光照强度的影响较大，在晴朗天气的12点至2点，光线充足，容易增加过曝程度，导致成像模糊或者色彩有明显不一致的情况。同时光照方向也决定了图像中目标物的明暗程度。</p>  
</div>
## 2.背景因素  
<div style="text-indent:2em">
<p>摄影成像考虑相片上相邻地物影像之间的密度差。如果地物影像之间没有密度差异，也就是没有影像反差，也就无法从影像上辨别地物。决定影像反差的因素除了地物本身特征外，还取决于阳光部分和阴影部分之间的差异。此外，不同季节背景差异较大。
</p>
</div>

## 3.相机因素  
<p>
(1)受相机设备的快门、光圈、ISO等参数值的设置影响，若ISO过高则画质降低；<br/>  
(2)受天气影响，影像易出现曝光过度或不足、影像的重影、散焦与噪点等问题;<br/>  
(3)设备本身的性能影响，如相机的物镜、像素、分辨率、噪音等，相机物镜对不同波长的光线折射率不同，在焦平面形成焦点产生横向色差和纵向色差而导致影响模糊不清晰，相机的像素是衡量分辨率的关键因素，等面积像素越多影像越清晰，细节表现越好，相机噪音容易引起图像杂点增多降低质量等。<br/>  
(4)受镜头自身凸透镜固有特性以及透镜本身与相机传感器（成像平面）或图像平面不平行而产生图像畸变。<br/>  
(5)当拍摄的背景地物纹理复杂，相机解算、压缩、存储的数据相对会大，当达到存储临界点相机无法及时响应快门信号，曝光动作出现滞后，容易造成丢片。<br/>  
</p>
## 4.飞行因素  
<div style="text-indent:2em">
<p>飞行高度影响飞行航片中的GSD（每个像素的实际大小），飞行高度的变化必然影响航片相幅大小，飞机离地面越近，GSD 数值越小，则精度越高；在高山等地区，无人机可能会遇到快速上下起伏情况，如果维持较小波动，可能因为拍摄距离变化，使摄像头拍摄到的画面模糊或数据失真。无人机与拍摄目标物的距离决定了图像中目标物的分辨率大小。当无人机与目标物较近时，目标物在图像中占比较大，分辨容易；无人机与目标物距离较远时，目标物在图像中占比小，识别困难。</p>
</div>
## 5.不可控因素  
<p> 遇到极少卫星信号瞬间失锁现象，造成数据异常。
</p>
# 二、无人机航拍影像的筛选方法     
筛选机制：图像内是否包含目标物；图像清晰度程度；图像重复率。

##  1.目标检测   
<div style="text-indent:2em">
<p> 线路目标：杆塔、导线、绝缘子、金具、附属设施（防震锤、驱鸟器、开口销、相序牌等）等。<br/>
    (1)基于回归的YOLO算法和SSD算法；<br/>
    (2)基于候选区域的Faster R-CNN算法； <br/>
    (3)……<br/>
</p>
</div>

## 2.模糊检测   
<p>
(1)Laplacian算法：模糊图片边界信息少，正常图片清晰边界信息大，通过计算图片二阶导得出密度变化快速的区域（边界），以方差阈值作为是否模糊的依据；<br/>  
(2)边缘锐度算法EAV：通过计算图像某一边缘的法线方向的灰度变化情况进行评价，近似统计边缘扩展函数能量分布作为判断依据；<br/>    
(3)梯度结构相似度算法NRSS：计算目标结构信息的变化感知图像失真值；<br/>    
(4)点锐度算法：对边缘锐度算法的计算改进，计算逐个像元领域梯度值，梯度值反映了图像灰度扩散程度，以灰度扩散程度作为判断依据； <br/>  (5)相邻像素灰度方差法（SMD）：图像越清晰，图像中高频分量越多，将灰度方差作为判断依据。 <br/>   
(6)二次模糊的清晰度算法：对原本清晰的图像进行模糊处理，高频分类的变化会比较大。对待测评的图像进行高斯模糊处理，得到图像的退化图像，以退化图像与原图像之间相邻像素的变化情况作为判断依据； <br/>   
(7)熵函数：利用统计特征的熵函数，在对焦过程中，熵函数越大图像越清晰，包含的信息量最多，将熵函数作为判断依据；  <br/>  
(8)能量梯度函数：将x方向与y方向的相邻像素灰度值之差的平方和作为每个像素点的梯度值，将所有像素梯度值累加作为清晰度判断依据；<br/>  
</p>
##  3.重复图像检测      
(1) Hash值重复图像检测：每幅图像对应特征经过变换后存储为图像的Hash值，将Hash值作为重复图像的判断依据；



### 参考资料  

<div id="refer-anchor-1"></div>-[1] [无人机在电力系统中的应用](https://zhuanlan.zhihu.com/p/67265940)   

<div id="refer-anchor-2"></div>-[2][影响无人机航测精度的因素](https://zhuanlan.zhihu.com/p/43955825)  

<div id="refer-anchor-3"></div>-[3][无人机航拍影响质量检查方法](https://zhuanlan.zhihu.com/p/118049990)  

<div id="refer-anchor-4"></div>-[4][图像的模糊检测方法](https://www.cnblogs.com/greentomlee/p/9379471.html)  

<div id="refer -anchor-5"></div>-[5] [图像清晰度评价方法 (https://wenku.baidu.com/view/59174c284b73f242336c5f6f.html)

<div id="refer-anchor-6"></div>-[6][无参考图像清晰度评价]( https://zhuanlan.zhihu.com/p/97024018)   

<div id="refer-anchor-7"></div>-[7][无参考图像清晰度评价](https://wenku.baidu.com/view/74e4d049767f5acfa1c7cdff.html)  

<div id="refer-anchor-8"></div>-[8][基于Hash值的重复图像检测算法] (https://wenku.baidu.com/view/f4745177a417866fb84a8e5e.html)  

