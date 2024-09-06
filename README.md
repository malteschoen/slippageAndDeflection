# slippageAndDeflection
## Introduction
Let us consider a very simple case of an extrusion die represented by an one-dimensional Eulerian beam subjected to a variable area load $p(x)$ (a variable melt pressure per mm of flow channel lenght, for example: 100 bar pressing down on a 20 mm wide channel correspond to 2e7 Newtons of force per meter of channel lenght).
* The area load/pressure follows the function of $y(x) = q(x) = x²$. 
* Our coordinate system has an a abcissa (x-axis) going from 0 to 1. Here, x = 0 represents the die outlet (zero bending moment as there is no clamping/restraint and zero pressure). Conversely, x = 1 represents the die inlet (maximum bending moment on account of the clamping/restraint present here; also maximum pressure).
* Our coordinate system also has an ordinate (y-axis) going from 0 to 1.
* This setting ensures that we have a steep pressure drop at the die inlet and a shallow, slip-affected pressure drop at the die outlet, see blue curve in figure 1.
  

![figure1](https://github.com/malteschoen/slippageAndDeflection/blob/main/figure1.png)

## Mathematical treatment
We primarily look at the bending moment (which is directly correlated to the strain of the outer fibre) instead of the deformation. Our bending moment $M$ must follow a formula looking like this
```math
M(x) =   \frac{x^4}{12}
```

to be in accordance the formula 
```math
\frac{d² M}{d²x}  = p(x) = x²
```
which prescribes a double differentiation of the bending moment to reconstruct the pressure curve.

## Interpretation
Now, in practical terms, what does this mean?
* Let us assume a 5 % positional error in the measurement of the bending moment. In simpler terms, the bending moment curve is stretched or compressed 'left to right'. See red, yellow and green curves in figure 2.
*  Our respective formulae for the highest and lowest bending moment become
 ```math
M(x) =   \frac{(1.05x)^4}{12} = 1.22 \frac{x^4}{12}
```
 ```math
M(x) =   \frac{(0.95x)^4}{12} = 0.81 \frac{x^4}{12}
```

* It follows that our reconstructed pressures would be:
```math
p(x) =   1.22x² 
```
 ```math
p(x) =   0.81x²
```
* Roughly 20 % of error are not acceptable for most applications.
