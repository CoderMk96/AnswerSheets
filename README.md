### 项目简介

#### 软件功能

基于opencv的答题卡识别

### 效果图

### 安装说明

python版本 3.6.4

opencv版本 3.4.1

### 更新日志

#### V1.0.0 版本

1. 对图片进行灰度化

2. 高斯模糊

3. 边缘检测

4. 轮廓检测，取最外层轮廓，得到有毛刺的外轮廓

5. 以轮廓周长的0.02倍为参数，进行多边形逼近，得到一个近似的外轮廓

6. 取近似出来的顶点为4的轮廓

7. 计算变换后的w和h，以及变换矩阵，并进行透视变换

8. 对透视变换后的图像，进行二值化

9. 轮廓检测，根据w,h>=20，和0.9<=w/h<=1.1为标准筛选轮廓

10. 对轮廓按照从上到下（y的大小）进行排序

11. 取出每排5个选项，再按从左到右（x的大小）进行排序

12. 遍历每一排的5个选项，按透视变换后的图像大小制作mask，并按取出的一个选项的轮廓进行填充白色

13. 将mask和二值化后的变换图像，进行与操作。

14. 通过cv2.countNonZero( )得出图像中非零像素的数量，最大值则为当前的选中项

15. 将选中项与预设好的答案进行比较，计算最终得分
