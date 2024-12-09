$
\textbf{Step 1: Problem Setup}
$

We are given data points $(t_j, \tilde{y}*j)$ for $ j = 1, \ldots, m $.

We want to find parameters $\alpha, \beta, \gamma \in \mathbb{R}$ such that the quadratic model
$$
y(t) = \alpha + \beta t + \gamma t^2
$$
best fits the data in a least-squares sense. That is, we want to minimize the objective function
$$
\phi(\alpha, \beta, \gamma) = \sum*{j=1}^m \bigl( \tilde{y}_j - (\alpha + \beta t_j + \gamma t_j^2) \bigr)^2.
$$

$
\textbf{Step 2: Least Squares Formulation}
$

To find the minimizing parameters, we set the partial derivatives of $\phi$ with respect to $\alpha, \beta, \gamma$ to zero.

Let
$
r_j(\alpha, \beta, \gamma) = \tilde{y}*j - (\alpha + \beta t_j + \gamma t_j^2)
$
be the residual for the $j$-th data point.

Then
$
\phi(\alpha, \beta, \gamma) = \sum*{j=1}^m r_j(\alpha,\beta,\gamma)^2.
$

The normal equations are derived as follows:

$
\frac{\partial \phi}{\partial \alpha} = \sum_{j=1}^m 2r_j(-1) = 0, \quad
\frac{\partial \phi}{\partial \beta} = \sum_{j=1}^m 2r_j(-t_j) = 0, \quad
\frac{\partial \phi}{\partial \gamma} = \sum_{j=1}^m 2r_j(-t_j^2) = 0.
$

Eliminating the factor 2, we have the system:

$
\sum_{j=1}^m (\tilde{y}*j - (\alpha + \beta t_j + \gamma t_j^2)) = 0,
$

$
\sum*{j=1}^m t_j(\tilde{y}*j - (\alpha + \beta t_j + \gamma t_j^2)) = 0,
$

$
\sum*{j=1}^m t_j^2(\tilde{y}_j - (\alpha + \beta t_j + \gamma t_j^2)) = 0.
$

Expanding these equations and grouping by $\alpha, \beta, \gamma$:

1. For the $\alpha$-equation:
   
   $
   \sum_{j=1}^m \tilde{y}*j = \alpha \sum*{j=1}^m 1 + \beta \sum_{j=1}^m t_j + \gamma \sum_{j=1}^m t_j^2.
   $

2. For the $\beta$-equation:
   
   $
   \sum_{j=1}^m t_j \tilde{y}*j = \alpha \sum*{j=1}^m t_j + \beta \sum_{j=1}^m t_j^2 + \gamma \sum_{j=1}^m t_j^3.
   $

3. For the $\gamma$-equation:
   
   $
   \sum_{j=1}^m t_j^2 \tilde{y}*j = \alpha \sum*{j=1}^m t_j^2 + \beta \sum_{j=1}^m t_j^3 + \gamma \sum_{j=1}^m t_j^4.
   $

In matrix form, let:
$$
S_0 = \sum_{j=1}^m 1 = m,\quad
S_1 = \sum_{j=1}^m t_j,\quad
S_2 = \sum_{j=1}^m t_j^2,\quad
S_3 = \sum_{j=1}^m t_j^3,\quad
S_4 = \sum_{j=1}^m t_j^4,
$$

and
$$
T_0 = \sum_{j=1}^m \tilde{y}*j,\quad
T_1 = \sum*{j=1}^m t_j \tilde{y}*j,\quad
T_2 = \sum*{j=1}^m t_j^2 \tilde{y}_j.
$$

Then the normal equations become:
$$
\begin{pmatrix}
S_0 & S_1 & S_2 \\
S_1 & S_2 & S_3 \\
S_2 & S_3 & S_4
\end{pmatrix}
\begin{pmatrix}
\alpha \\ \beta \\ \gamma
\end{pmatrix}
=
\begin{pmatrix}
T_0 \\ T_1 \\ T_2
\end{pmatrix}
\Rightarrow
\begin{pmatrix}
\sum_{j=1}^m \tilde{y}*j \\
\sum_{j=1}^m t_j \tilde{y}*j \\
\sum_{j=1}^m t_j^2 \tilde{y}_j
\end{pmatrix}.
$$

$
\textbf{Step 3: Solving the System}
$

Solving the $3 \times 3$ linear system for $\alpha, \beta, \gamma$ gives us the least-squares solution.