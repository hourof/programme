# 1.plt.plot()绘图

> **作用:** 可以画曲线和直线

**示例:**

> ```python
> import numpy as np
> import matplotlib.pyplot as plt
> 
> # 构造曲线上的点
> curve = np.array([[0, 0], [1, 2], [2, 3], [3, 3]])
> 
> # 绘制曲线
> plt.plot(curve[:, 0], curve[:, 1], label="Example Curve")
> 
> # 显示图例
> plt.legend()
> plt.show()
> ```
>
> 

它会 **将** `(0,0) → (1,2) → (2,3) → (3,3)` **连接成一条折线**

**效果:**

![plot](img\plot.png)

# 2. plt.scatter()画点

**作用:**在plt图像中画点

**示例:**

```python
import numpy as np
import matplotlib.pyplot as plt

# 构造曲线上的点
curve = np.array([[0, 0], [1, 2], [2, 3], [3, 3]])
# 绘制曲线
plt.plot(curve[:, 0], curve[:, 1], label="Example Curve")
plt.scatter(*zip(*curve),color = "red",label = "la")
# 显示图例
plt.legend()
plt.show()
```

**效果:**

![Example_Curve](img\Example_Curve.png)
