# fractals
Mandelbulb fractal 3D in pure Javascript based on [GPU.JS](https://github.com/gpujs/gpu.js)

[Run Mandelbulb!](https://kamil-kielczewski.github.io/fractals/mandelbulb.html)

## Calc Ray

Input parameters ([left-handed coordinate system](https://en.wikipedia.org/wiki/Cartesian_coordinate_system#In_three_dimensions)): 
* $E = [Ex,Ey,Ez]$ - camera (eye) position at point 
* $T= [Tx,Ty,Tz]$ - target point where camera looks  
* $w=[wx,wy,wz]$ - camera vertical normalized vector which idicates where is up and were is down (not shown on picture, usually equal [0,1,0]). 
* $\theta \in [0,\pi)$ - field of view (slacar value, for human eye $\approx 90^\circ$)
* $k$ - number of pixels on screen width 
* $m$ - number of pixels screen in height 

<p align="center"><img src="/tex/raysMatrix.png" align=middle /></p>

**IDEA**: lets find position of center of each pixel $P_{ij}$ which allows us to easily find ray which starts at $E$ and go thought that pixel. To do it we find first $P_{1m}$ and find others by move on vievports plane.

**ASSUMPTION**: $d=1$ which simplify calculations but not change the result (because $r_{ij}$ is normalized and viewport size is determined by $k,m$ and $\theta$) 

**PRECALCULATIONS**: First we calculate normalized vectors $v_n, b_n$ from picutre (which are parallel to viewport plane and give as direction for shifting)

$$t = T-E, \qquad b = w\times t  $$

$$ 
t_n = \frac{t}{||t||}, \qquad
b_n = \frac{b}{||b||}, \qquad
v_n = t_n\times b_n \\ 
$$

notice: $C=E+t_nd$, then we calculate viewport size divided by 2 and including aspect ratio $\frac{m}{k}$

$$g_x=\frac{h_x}{2} =d \tan \frac{\theta}{2}, \qquad  g_y =\frac{h_y}{2} = g_x \frac{m}{k}$$

and then we calculate shifting vectors $q_x,q_y$ on viewport $x,y$ direction and viewport left upper pixel

$$ q_x = \frac{2g_x}{k-1}b_n, \qquad
q_y = \frac{2g_y}{m-1}v_n, \qquad
p_{1m} = t_n d - g_xb_n - g_yv_n$$



**CALCULATIONS**: notice that $P_{ij} = E + p_{ij}$ and ray $R_{ij} = P_{ij} -E = p_{ij}$ so normalized ray $r_{ij}$ is 

$$ p_{ij} = p_{1m} + q_x(i-1) + q_y(j-1)$$
$$ r_{ij} = \frac{p_{ij}}{||p_{ij}||} $$


## Ray marching (calc ray color)



