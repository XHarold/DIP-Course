# 图像旋转矩阵推导

### 旋转矩阵的基本形式

在二维平面上，围绕原点 (0, 0) **顺时针**旋转角度 \(\theta\) 的旋转矩阵 \(R\) 表示为：
\[ R = \begin{bmatrix}
\cos\theta & \sin\theta \\
-\sin\theta & \cos\theta
\end{bmatrix} \]


为了围绕任意点 (x0, y0) 进行旋转，进行以下步骤：

1. 将图像平移，使得旋转中心 (x0, y0) 移动到原点 (0, 0)。
2. 围绕原点 (0, 0) 进行旋转。
3. 将图像平移回原来的位置。

### 平移矩阵

使得旋转中心 (x0, y0) 移动到原点 (0, 0)的平移矩阵 \(T_{1}\) 表示为：
\[ T_{1} = \begin{bmatrix}
1 & 0 & -x0 \\
0 & 1 & -y0 \\
0 & 0 & 1
\end{bmatrix} \]

移动回来的平移矩阵 \(T_{2}\) 表示为：
\[ T_{2} = \begin{bmatrix}
1 & 0 & x0 \\
0 & 1 & y0 \\
0 & 0 & 1
\end{bmatrix} \]

### 旋转矩阵

在齐次坐标系中，围绕原点 (0, 0) 旋转角度 \(\theta\) 的旋转矩阵 \(R\) 表示为：
\[ R = \begin{bmatrix}
\cos\theta & \sin\theta & 0 \\
-\sin\theta & \cos\theta & 0 \\
0 & 0 & 1
\end{bmatrix} \]

### 综合变换矩阵

将上述三个矩阵结合起来，得到围绕任意点 (x0, y0) 旋转角度 \(\theta\) 的综合变换矩阵 \(T\)：
\[ T = T_{2} \cdot R \cdot T_{1} \]

即：
\[ T = \begin{bmatrix}
1 & 0 & x0 \\
0 & 1 & y0 \\
0 & 0 & 1
\end{bmatrix} \cdot \begin{bmatrix}
\cos\theta & \sin\theta & 0 \\
-\sin\theta & \cos\theta & 0 \\
0 & 0 & 1
\end{bmatrix} \cdot \begin{bmatrix}
1 & 0 & -x0 \\
0 & 1 & -y0 \\
0 & 0 & 1
\end{bmatrix} \]

通过矩阵乘法计算得到：
\[ T = \begin{bmatrix}
\cos\theta & \sin\theta & x0 - x0\cos\theta - y0\sin\theta \\
-\sin\theta & \cos\theta & y0 + x0\sin\theta - y0\cos\theta \\
0 & 0 & 1
\end{bmatrix} \]

