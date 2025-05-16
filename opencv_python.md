# 1.模板匹配教程

> 模板匹配主要功能解释在主图中寻找模板图

- 读取一张主图 (`image.jpg`) 和一个模板图 (`template.jpg`)  
- 使用 `cv2.matchTemplate()` 进行模板匹配  
- 画出匹配位置的矩形框  

## 1.代码示例
```python
import cv2
import numpy as np

# 读取主图和模板图
image = cv2.imread("image.jpg", cv2.IMREAD_COLOR)
template = cv2.imread("template.jpg", cv2.IMREAD_COLOR)

# 获取模板图尺寸
w, h = template.shape[1], template.shape[0]

# 进行模板匹配
result = cv2.matchTemplate(image, template, cv2.TM_CCOEFF_NORMED)

# 设置匹配阈值
threshold = 0.8
locations = np.where(result >= threshold)

# 在匹配区域绘制矩形
for pt in zip(*locations[::-1]):  # 转换坐标格式
    cv2.rectangle(image, pt, (pt[0] + w, pt[1] + h), (0, 255, 0), 2)

# 显示结果
cv2.imshow("Matched Image", image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

## 2.代码说明
1. **读取主图和模板图**，确保两者格式一致 (`cv2.IMREAD_COLOR`)。  
2. **执行模板匹配**，使用 `cv2.TM_CCOEFF_NORMED` 算法找出相似区域。  
3. **设定阈值** (`threshold = 0.8`)，只显示匹配度高于 `0.8` 的区域。  
4. **用 `cv2.rectangle()` 标注匹配区域**，绘制绿色边框。  
5. **显示结果**，如果匹配成功，窗口会显示高亮标记的匹配区域。  

---

🔹 **你可以试试调整 `threshold`**（比如 `0.7`），看看检测结果是否发生变化！  
🔹 **如果需要更精确的匹配**，可以结合 **多尺度匹配、边缘检测或自适应阈值** 进行优化。  



# 2.opencv刷面试题和github开源项目

## 1.背100到

​	https://blog.csdn.net/qq_38334677/article/details/134356728

## 2.

​	[opencv- CSDN搜索](https://so.csdn.net/so/search?q=opencv&t=blog&u=qq_38334677)

## 3.这个博主有很多个博客,直接点他头像，在博客栏搜索opencv就行

## 4.opencv机器学习项目

[mbeyeler/opencv-machine-learning: M. Beyeler (2017). Machine Learning for OpenCV: Intelligent image processing with Python. Packt Publishing Ltd., ISBN 978-178398028-4.](https://github.com/mbeyeler/opencv-machine-learning)

## 5.opencv玩游戏来做项目

[learncodebygaming/opencv_tutorials: Tutorials for learning OpenCV by making a video game bot.](https://github.com/learncodebygaming/opencv_tutorials)

## 6.opencv实用项目

[luohenyueji/OpenCV-Practical-Exercise：OpenCV 实](https://github.com/luohenyueji/OpenCV-Practical-Exercise)

## 7.图像处理玩枪战训练游戏

作者：Tim Pearce, Jun Zhu
论文：https://arxiv.org/abs/2104.04258
项目：Counter-Strike_Behavioural_Cloning
