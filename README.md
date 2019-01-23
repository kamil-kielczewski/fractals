# fractals
Mandelbulb fractal 3D in pure Javascript based on [GPU.JS](https://github.com/gpujs/gpu.js)

[Run Mandelbulb!](https://kamil-kielczewski.github.io/fractals/mandelbulb.html)

## Calc Ray

Input parameters: 
* <img src="/tex/d62fbe219457fce60682a162b4ecbab4.svg?invert_in_darkmode&sanitize=true" align=middle width=124.40236709999998pt height=24.65753399999998pt/> - camera (eye) position at point 
* <img src="/tex/aecdc767c97bdaf680b7c57d54dbe69d.svg?invert_in_darkmode&sanitize=true" align=middle width=119.63090204999997pt height=24.65753399999998pt/> - target point where camera looks  
* <img src="/tex/356dfd3a8b76763cdf8121889b66694a.svg?invert_in_darkmode&sanitize=true" align=middle width=120.91704239999997pt height=24.65753399999998pt/> - camera vertical normalized vector which idicates where is up and were is down (not shown on picture, usually equal [0,1,0]). 
* <img src="/tex/76d6aadfeff939454320a586205bb263.svg?invert_in_darkmode&sanitize=true" align=middle width=77.57983364999998pt height=24.65753399999998pt/> - field of view (slacar value, for human eye <img src="/tex/9e55bdb7fdbca783335bc66dc13b0ed2.svg?invert_in_darkmode&sanitize=true" align=middle width=40.52514509999999pt height=22.63850490000001pt/>)
* <img src="/tex/63bb9849783d01d91403bc9a5fea12a2.svg?invert_in_darkmode&sanitize=true" align=middle width=9.075367949999992pt height=22.831056599999986pt/> - number of pixels on screen width 
* <img src="/tex/0e51a2dede42189d77627c4d742822c3.svg?invert_in_darkmode&sanitize=true" align=middle width=14.433101099999991pt height=14.15524440000002pt/> - number of pixels screen in height 

<p align="center"><img src="/tex/raysMatrix.png" align=middle /></p>

pre-calculations (we can assume that <img src="/tex/4cfe92e893a7541f68473ecb08419237.svg?invert_in_darkmode&sanitize=true" align=middle width=38.69280359999998pt height=22.831056599999986pt/> - it doesn't matter siecne <img src="/tex/27e556cf3caa0673ac49a8f0de3c73ca.svg?invert_in_darkmode&sanitize=true" align=middle width=8.17352744999999pt height=22.831056599999986pt/> determine viewport size)

<p align="center"><img src="/tex/eacad8882da6be25f2da50d30bca4304.svg?invert_in_darkmode&sanitize=true" align=middle width=156.07879155pt height=163.88124059999998pt/></p>

and (notice: <img src="/tex/36727b27e5df89ce2c1697714217ed85.svg?invert_in_darkmode&sanitize=true" align=middle width=82.07775674999999pt height=22.465723500000017pt/>)

<p align="center"><img src="/tex/fdcd319210d06a2447316c2a204b7cb3.svg?invert_in_darkmode&sanitize=true" align=middle width=163.13735625pt height=100.38210435pt/></p>

Final calculations for ray <img src="/tex/92e0822b1528090efc2435d2ae60c9ee.svg?invert_in_darkmode&sanitize=true" align=middle width=18.17172884999999pt height=14.15524440000002pt/> for each pixel (notice: <img src="/tex/960053e3edfbd4549965e659744804ef.svg?invert_in_darkmode&sanitize=true" align=middle width=96.24790395pt height=22.465723500000017pt/> )

<p align="center"><img src="/tex/7ddc31944b8872363eb9411ab8976073.svg?invert_in_darkmode&sanitize=true" align=middle width=215.909397pt height=41.68947585pt/></p>





