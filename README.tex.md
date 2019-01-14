# fractals
Mandelbulb fractal 3D in pure Javascript based on [GPU.JS](https://github.com/gpujs/gpu.js)

[Run Mandelbulb!](https://kamil-kielczewski.github.io/fractals/mandelbulb.html)

## Calc Ray

Input parameters: 
* $E = [Ex,Ey,Ez]$ - camera (eye) position at point 
* $T= [Tx,Ty,Tz]$ - target point where camera looks  
* $w=[wx,wy,wz]$ - camera vertical normalized vector which idicates where is up and were is down (not shown on picture, usually equal [0,1,0]). 
* $\theta \in [0,360]$ - field of view (slacar value, for human eye $\approx 90^\circ$)
* $k$ - number of pixels on screen width 
* $m$ - number of pixels screen in height 

<p align="center"><img src="/tex/raysMatrix.png" align=middle /></p>

pre-calculations

$$
\begin{align}
t &= T-E \\
t_n &= t/||t|| \\
b &= w\times t \\
b_n &= b/||b|| \\
v_n &= b_n\times t_n \\
g_x &=h_x/2 = \tan(\theta/4) \\
g_y &=h_y/2 = g_x m/k \\
\end{align}
$$

and

$$
\begin{align}
p &= \frac{2g_x}{k-1}b_n \\ 
q &= \frac{2g_y}{m-1}v_n \\ 
p_{11} &= t_n - g_xb_n +  g_yv_n \\
\end{align}
$$

Final calculations for ray $r_{ij}$ for each pixel (I put $p_{ij},P_{ij}$ for theoretical reason but they will be not used further)

$$
\begin{align}
p_{ij} &= p_{11} + (i-1)p + (j-1)q \\
P_{ij} &= E + p_{ij} \\
r_{ij} &= p_{ij}/||p_{ij}|| \\
\end{align}
$$





