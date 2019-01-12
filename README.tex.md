# fractals
Currently Mandelbulb fractal

[Run Mandelbulb!](https://kamil-kielczewski.github.io/fractals/mandelbulb.html)

## Calc Ray

<p align="center"><img src="/tex/raysMatrix.png" align=middle /></p>

We  need camera (eye) position at point $E = [Ex,Ey,Ez]$, target point where camera looks $T= [Tx,Ty,Tz]$, camera vertical normalized vector (which idicates where is up and were is down)  $v=[vx,vy,vz]$. We also need field of view scalar $f \in [0,360]$ (human eye $~90^\circ$) and $k$ with number of pixels on screen width and $m$ with number of pixels screen in height :

$$
\begin{align}
t &= T-E \\
t_n &= t/||t|| \\
b &= v\times t \\
b_n &= b/||b|| \\
w_n &= b_n\times t_n \\
h_x &= 2\tan(f/4) \\
h_y &= h_x m/k \\
\end{align}
$$

and

$$
\begin{align}
p &= \frac{h_x}{k-1}b_n \\ 
q &= \frac{h_y}{m-1}w_n \\ 
p_{11} &= t_n - \frac{h_x}{2}b_n +  \frac{h_y}{2}w_n \\
p_{ij} &= p_{11} + (i-1)p + (j-1)q \\
\end{align}
$$

$$
r_{ij} &= p_{ij}/||p_{ij}|| \\
P_{ij} &= E + r_{ij} \\
$$




TODO: develop this documentation



