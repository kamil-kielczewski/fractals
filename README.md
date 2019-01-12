# fractals
Currently Mandelbulb fractal

[Run Mandelbulb!](https://kamil-kielczewski.github.io/fractals/mandelbulb.html)

## Calc Ray

Input parameters: 
* <img src="/tex/d62fbe219457fce60682a162b4ecbab4.svg?invert_in_darkmode&sanitize=true" align=middle width=124.40236709999998pt height=24.65753399999998pt/> - camera (eye) position at point 
* <img src="/tex/aecdc767c97bdaf680b7c57d54dbe69d.svg?invert_in_darkmode&sanitize=true" align=middle width=119.63090204999997pt height=24.65753399999998pt/> - target point where camera looks  
* <img src="/tex/356dfd3a8b76763cdf8121889b66694a.svg?invert_in_darkmode&sanitize=true" align=middle width=120.91704239999997pt height=24.65753399999998pt/> - camera vertical normalized vector which idicates where is up and were is down (not shown on picture, usually equal [0,1,0]). 
* <img src="/tex/ff73c224f59f9c37802c1c71f6b4b819.svg?invert_in_darkmode&sanitize=true" align=middle width=79.22372039999998pt height=24.65753399999998pt/> - field of view (slacar value, for human eye <img src="/tex/9e55bdb7fdbca783335bc66dc13b0ed2.svg?invert_in_darkmode&sanitize=true" align=middle width=40.52514509999999pt height=22.63850490000001pt/>)
* <img src="/tex/63bb9849783d01d91403bc9a5fea12a2.svg?invert_in_darkmode&sanitize=true" align=middle width=9.075367949999992pt height=22.831056599999986pt/> - number of pixels on screen width 
* <img src="/tex/0e51a2dede42189d77627c4d742822c3.svg?invert_in_darkmode&sanitize=true" align=middle width=14.433101099999991pt height=14.15524440000002pt/> - number of pixels screen in height 

<p align="center"><img src="/tex/raysMatrix.png" align=middle /></p>

pre-calculations

<p align="center"><img src="/tex/baa7ad5fe0e0690223fa5922e588c018.svg?invert_in_darkmode&sanitize=true" align=middle width=113.40948795pt height=163.88124059999998pt/></p>

and

<p align="center"><img src="/tex/313b4f9a24c24ee0538079152302936d.svg?invert_in_darkmode&sanitize=true" align=middle width=0.0pt height=0.0pt/></p>

Final calculations for each pixel (<img src="/tex/ca20b61a0f91c4fb2deaac14f1920db4.svg?invert_in_darkmode&sanitize=true" align=middle width=48.462788549999985pt height=22.465723500000017pt/> are not used further)

<p align="center"><img src="/tex/0307fd9d9b567ad4ec511cdb851d563a.svg?invert_in_darkmode&sanitize=true" align=middle width=218.19249539999998pt height=66.34700985pt/></p>





