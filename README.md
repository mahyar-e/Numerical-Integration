# Numerical-Integration

In analysis, numerical integration comprises a broad family of algorithms for calculating the numerical value of a definite integral. The term numerical quadrature (often abbreviated to quadrature) is more or less a synonym for "numerical integration", especially as applied to one-dimensional integrals. Some authors refer to numerical integration over more than one dimension as cubature; others take "quadrature" to include higher-dimensional integration.

The basic problem in numerical integration is to compute an approximate solution to a definite integral

$$\int_{a}^{b}f(x)dx$$

to a given degree of accuracy. If f(x) is a smooth function integrated over a small number of dimensions, and the domain of integration is bounded, there are many methods for approximating the integral to the desired precision.

Numerical integration has roots in the geometrical problem of finding a square with the same area as a given plane figure (quadrature or squaring), as in the quadrature of the circle. The term is also sometimes used to describe the numerical solution of differential equations.


In this code, we are going to see four ways of calculating an integral numerically.

### 1- The square integration method:

$$\int_{a}^{b}f(x)dx = \sum_{i=0}^{N-1} \Delta x_i f(x_i) $$

$$\Delta x_i = \frac{b-a}{N} $$

$$\int_{a}^{b}f(x)dx = \frac{b-a}{N} [f(x_0) + f(x_1) + \dots + f(x_{N-1})] $$

$$\int_{a}^{b}f(x)dx = \frac{b-a}{N} \sum_{i=0}^{N-1} f(x_i) $$

This method is pretty straightforward. We are literally calculating the areas of $N - 1$ squares below the desired function.

### 2- The tarpezoidal integration method:

$$ \int_{a}^{b}f(x)dx = \frac{\Delta x}{2} [f(x_0) + 2 \sum^{N-1}_{i=1} f(x_i) + f(x_n)]  $$

$$ \int_{a}^{b}f(x)dx = \frac{b - a}{2 N} [f(x_0) + 2 \sum^{N-1}_{i=1} f(x_i) + f(x_n)]  $$

In this method, we are calculating the trapezoids under the function. This is somehow the first order approximation, because we are fitting a line on the plot between two points and calculating the area of  the trapezoid below the tangent line.  


### 3- The Simpson integration method:


$$ \int_{a}^{b}f(x)dx = \frac{\Delta x}{3} [f(x_0) + 4 \sum^{N-1}_{2i + 1 =1}f(x_i) + 2 \sum^{N-2}_{2i=1} f(x_i) +f(x_n)] $$

$$ \int_{a}^{b}f(x)dx = \frac{\Delta x}{3} [f(x_0) + 4 {\sum^{N-1}_{i=1, 3, 5} f(x_i)} + 2 {\sum^{N-2}_{i=2, 4, 6} f(x_i)} +f(x_n)]$$

$$ \int_{a}^{b}f(x)dx = \frac{\Delta x}{3} [f(x_0) + 4 \sum^{N-1}_{i=1, 3, 5} f(x_i) + 2 \sum^{N-2}_{i=2, 4, 6} f(x_i) +f(x_n)] $$


$$ \int_{a}^{b}f(x)dx = \frac{b - a}{3 N} [f(x_0) + 4 \sum^{N-1}_{i=1, 3, 5} f(x_i) + 2 \sum^{N-2}_{i=2, 4, 6} f(x_i) +f(x_n)] $$

