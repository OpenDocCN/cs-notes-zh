# 015：线性递归方程的求解

![](img/b36caa3b62ff386d082bd1ea25cce10a_1.png)

![](img/b36caa3b62ff386d082bd1ea25cce10a_2.png)

在本节课中，我们将学习如何求解线性齐次递归方程。我们将从二阶递归方程开始，推导出通用的求解公式，并探讨如何将这种方法推广到更高阶的递归方程。

---

## 二阶线性递归方程的求解

上一节我们介绍了斐波那契数列的求解方法。本节中，我们来看看如何将这种方法推广到一般形式的二阶线性递归方程。

假设我们有一个递归方程，其形式为：
\[
A_n = B \cdot A_{n-1} + C \cdot A_{n-2}
\]
其中，\( B \) 和 \( C \) 是常数。我们的目标是找到一个关于 \( n \) 的显式公式来表示 \( A_n \)。

### 建立矩阵方程

求解的第一步是将递归关系转化为矩阵形式。

以下是建立矩阵方程的步骤：
1.  我们定义状态向量为 \( \begin{bmatrix} A_{n+1} \\ A_n \end{bmatrix} \)。
2.  根据递归关系 \( A_{n+1} = B \cdot A_n + C \cdot A_{n-1} \)，我们可以写出：
    \[
    \begin{bmatrix} A_{n+1} \\ A_n \end{bmatrix} = \begin{bmatrix} B & C \\ 1 & 0 \end{bmatrix} \cdot \begin{bmatrix} A_n \\ A_{n-1} \end{bmatrix}
    \]
3.  通过反复应用这个关系，我们可以得到：
    \[
    \begin{bmatrix} A_{n+1} \\ A_n \end{bmatrix} = \begin{bmatrix} B & C \\ 1 & 0 \end{bmatrix}^n \cdot \begin{bmatrix} A_1 \\ A_0 \end{bmatrix}
    \]

现在，问题的核心转化为计算矩阵 \( \begin{bmatrix} B & C \\ 1 & 0 \end{bmatrix} \) 的 \( n \) 次幂。

### 矩阵对角化

为了高效地计算矩阵的幂，我们采用对角化的方法。对角化的核心是寻找矩阵的特征值和特征向量。

我们需要找到标量 \( \lambda \)（特征值）和非零向量 \( \mathbf{v} \)（特征向量），使得：
\[
\begin{bmatrix} B & C \\ 1 & 0 \end{bmatrix} \cdot \mathbf{v} = \lambda \cdot \mathbf{v}
\]
这等价于求解方程：
\[
(\begin{bmatrix} B & C \\ 1 & 0 \end{bmatrix} - \lambda \mathbf{I}) \cdot \mathbf{v} = \mathbf{0}
\]
其中 \( \mathbf{I} \) 是单位矩阵。这个方程有非零解 \( \mathbf{v} \) 的条件是系数矩阵的行列式为0：
\[
\det \begin{bmatrix} B - \lambda & C \\ 1 & -\lambda \end{bmatrix} = 0
\]
计算行列式，我们得到特征方程：
\[
(B - \lambda)(-\lambda) - C \cdot 1 = 0
\]
化简后得到：
\[
\lambda^2 - B\lambda - C = 0
\]
这个二次方程的根 \( \lambda_1 \) 和 \( \lambda_2 \) 就是我们需要的特征值。

**重要提示**：如果 \( \lambda_1 \neq \lambda_2 \)，那么对应的特征向量 \( \mathbf{v}_1 \) 和 \( \mathbf{v}_2 \) 线性无关（即，一个不是另一个的倍数）。这保证了由这些特征向量组成的矩阵是可逆的，从而能够成功对角化。

### 得到通解公式

假设我们找到了两个不同的特征值 \( \lambda_1 \) 和 \( \lambda_2 \)，以及对应的特征向量。我们可以将原矩阵对角化：
\[
\begin{bmatrix} B & C \\ 1 & 0 \end{bmatrix} = P \begin{bmatrix} \lambda_1 & 0 \\ 0 & \lambda_2 \end{bmatrix} P^{-1}
\]
其中，矩阵 \( P \) 的列是特征向量 \( \mathbf{v}_1 \) 和 \( \mathbf{v}_2 \)。

那么，矩阵的 \( n \) 次幂就很容易计算：
\[
\begin{bmatrix} B & C \\ 1 & 0 \end{bmatrix}^n = P \begin{bmatrix} \lambda_1^n & 0 \\ 0 & \lambda_2^n \end{bmatrix} P^{-1}
\]
将这个结果代入我们的矩阵方程：
\[
\begin{bmatrix} A_{n+1} \\ A_n \end{bmatrix} = P \begin{bmatrix} \lambda_1^n & 0 \\ 0 & \lambda_2^n \end{bmatrix} P^{-1} \cdot \begin{bmatrix} A_1 \\ A_0 \end{bmatrix}
\]
经过矩阵乘法运算（结果包含一些由初始条件 \( A_0, A_1 \) 和矩阵 \( P \) 决定的常数），最终我们可以将 \( A_n \) 表示为：
\[
A_n = \alpha \lambda_1^n + \beta \lambda_2^n
\]
其中，常数 \( \alpha \) 和 \( \beta \) 可以通过代入初始条件 \( A_0 \) 和 \( A_1 \) 来求解。

---

## 向三阶递归方程的推广

理解了二阶方程的求解后，我们自然想知道如何求解更高阶的方程。本节中，我们来看看三阶线性递归方程。

考虑一个三阶线性齐次递归方程：
\[
A_n = A \cdot A_{n-1} + B \cdot A_{n-2} + C \cdot A_{n-3}
\]
其中 \( A, B, C \) 是常数。

### 建立三阶矩阵方程

我们可以采用类似的方法，将其转化为矩阵形式。

以下是建立三阶矩阵方程的步骤：
1.  我们定义状态向量为 \( \begin{bmatrix} A_{n+1} \\ A_n \\ A_{n-1} \end{bmatrix} \)。
2.  根据递归关系，我们可以写出：
    \[
    \begin{bmatrix} A_{n+1} \\ A_n \\ A_{n-1} \end{bmatrix} = \begin{bmatrix} A & B & C \\ 1 & 0 & 0 \\ 0 & 1 & 0 \end{bmatrix} \cdot \begin{bmatrix} A_n \\ A_{n-1} \\ A_{n-2} \end{bmatrix}
    \]
3.  同样地，通过递推得到：
    \[
    \begin{bmatrix} A_{n+1} \\ A_n \\ A_{n-1} \end{bmatrix} = \begin{bmatrix} A & B & C \\ 1 & 0 & 0 \\ 0 & 1 & 0 \end{bmatrix}^n \cdot \begin{bmatrix} A_2 \\ A_1 \\ A_0 \end{bmatrix}
    \]

### 三阶矩阵的对角化

现在，我们需要对角化这个3x3矩阵 \( M = \begin{bmatrix} A & B & C \\ 1 & 0 & 0 \\ 0 & 1 & 0 \end{bmatrix} \)。这需要找到三个特征值 \( \lambda_1, \lambda_2, \lambda_3 \) 和对应的特征向量 \( \mathbf{v}_1, \mathbf{v}_2, \mathbf{v}_3 \)，满足：
\[
M \cdot \mathbf{v}_i = \lambda_i \cdot \mathbf{v}_i, \quad i = 1, 2, 3
\]
如果这三个特征值互不相同（\( \lambda_1 \neq \lambda_2 \neq \lambda_3 \)），那么可以证明对应的特征向量是线性无关的。这意味着由这些特征向量组成的矩阵 \( P = [\mathbf{v}_1, \mathbf{v}_2, \mathbf{v}_3] \) 是可逆的。

**线性无关性的证明思路**：假设存在不全为零的常数 \( c_1, c_2, c_3 \)，使得 \( c_1\mathbf{v}_1 + c_2\mathbf{v}_2 + c_3\mathbf{v}_3 = \mathbf{0} \)。我们可以用矩阵 \( M \) 左乘这个等式，并利用 \( M\mathbf{v}_i = \lambda_i \mathbf{v}_i \) 的性质，得到另一个关于 \( \lambda_i \) 和 \( \mathbf{v}_i \) 的线性组合等于零的等式。通过将原等式乘以某个 \( \lambda_i \) 后与新等式相减等操作，并利用特征值互异和二阶情形中已证明的结论（不同特征值对应的特征向量不成比例），可以推导出矛盾，从而证明 \( c_1 = c_2 = c_3 = 0 \)。因此，向量组线性无关。

一旦矩阵可对角化，我们就有：
\[
M = P \begin{bmatrix} \lambda_1 & 0 & 0 \\ 0 & \lambda_2 & 0 \\ 0 & 0 & \lambda_3 \end{bmatrix} P^{-1}
\]
进而：
\[
M^n = P \begin{bmatrix} \lambda_1^n & 0 & 0 \\ 0 & \lambda_2^n & 0 \\ 0 & 0 & \lambda_3^n \end{bmatrix} P^{-1}
\]
最终，\( A_n \) 的通解形式为：
\[
A_n = \alpha \lambda_1^n + \beta \lambda_2^n + \gamma \lambda_3^n
\]
其中常数 \( \alpha, \beta, \gamma \) 由初始条件 \( A_0, A_1, A_2 \) 确定。

---

## 总结

![](img/b36caa3b62ff386d082bd1ea25cce10a_4.png)

本节课中我们一起学习了求解线性齐次递归方程的系统方法。
1.  对于二阶递归 \( A_n = B A_{n-1} + C A_{n-2} \)，我们通过将其转化为矩阵方程并利用对角化技术，得到了通解 \( A_n = \alpha \lambda_1^n + \beta \lambda_2^n \)，其中 \( \lambda_1, \lambda_2 \) 是特征方程 \( \lambda^2 - B\lambda - C = 0 \) 的根。
2.  这种方法可以推广到更高阶。对于三阶递归 \( A_n = A A_{n-1} + B A_{n-2} + C A_{n-3} \”，我们同样构建矩阵并寻求对角化。如果找到三个互异的特征值，就能得到形如 \( A_n = \alpha \lambda_1^n + \beta \lambda_2^n + \gamma \lambda_3^n \) 的通解。
3.  求解的关键步骤包括：建立矩阵方程、求解特征值和特征向量、对角化矩阵、利用初始条件确定组合系数。当特征值出现重根时，情况会稍复杂，我们将在后续课程中讨论。