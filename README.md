# Numerical-Integration

In analysis, numerical integration comprises a broad family of algorithms for calculating the numerical value of a definite integral. The term numerical quadrature (often abbreviated to quadrature) is more or less a synonym for "numerical integration", especially as applied to one-dimensional integrals. Some authors refer to numerical integration over more than one dimension as cubature; others take "quadrature" to include higher-dimensional integration.

The basic problem in numerical integration is to compute an approximate solution to a definite integral

$$\int_{a}^{b}f(x)dx$$

to a given degree of accuracy. If f(x) is a smooth function integrated over a small number of dimensions, and the domain of integration is bounded, there are many methods for approximating the integral to the desired precision.

Numerical integration has roots in the geometrical problem of finding a square with the same area as a given plane figure (quadrature or squaring), as in the quadrature of the circle. The term is also sometimes used to describe the numerical solution of differential equations.


In this code, we are going to see four ways of calculating an integral numerically.

![The-numerical-integration-methods-analysed-in-19_W640](https://github.com/mahyar-e/Numerical-Integration/assets/78594407/face6702-f229-43c4-bfb5-3763a4ae0c05)

from [Research trends and challenges on DAC testing](https://www.researchgate.net/publication/342583119_Research_trends_and_challenges_on_DAC_testing/figures)

### 1- The square integration method:

$$\int_{a}^{b}f(x)dx = \sum_{i=0}^{N-1} \Delta x_i f(x_i) $$

$$\Delta x_i = \frac{b-a}{N} $$

$$\int_{a}^{b}f(x)dx = \frac{b-a}{N} [f(x_0) + f(x_1) + \dots + f(x_{N-1})] $$

$$\int_{a}^{b}f(x)dx = \frac{b-a}{N} \sum_{i=0}^{N-1} f(x_i) $$

This method is pretty straightforward. We are literally calculating the areas of $N - 1$ squares below the desired function.

### 2- The tarpezoidal integration method:

$$ \int_{a}^{b}f(x)dx = \frac{\Delta x}{2} [f(x_0) + 2 \sum^{N-1}_{i=1} f(x_i) + f(x_n)]  $$

$$ \int_{a}^{b}f(x)dx = \frac{b - a}{2 N} [f(x_0) + 2 \sum^{N-1}_{i=1} f(x_i) + f(x_n)]  $$

![21 03 1-Trapezoid_integral](https://github.com/mahyar-e/Numerical-Integration/assets/78594407/53984d93-9047-45ef-ab52-9e33f4ac1a02)

In this method, we are calculating the trapezoids under the function. This is somehow the first order approximation, because we are fitting a line on the plot between two points and calculating the area of  the trapezoid below the tangent line.  


### 3- The Simpson integration method:

$$ \int_{a}^{b}f(x)dx = \frac{\Delta x}{3} (f(x_0) + 4 \sum^{N-1}_{i=1, 3, 5} f(x_i) + 2 \sum^{N-2}_{i=2, 4, 6} f(x_i) +f(x_n)) $$

$$ \int_{a}^{b}f(x)dx = \frac{b - a}{3 N} (f(x_0) + 4 \sum^{N-1}_{i=1, 3, 5} f(x_i) + 2 \sum^{N-2}_{i=2, 4, 6} f(x_i) +f(x_n)) $$

Simpson method is the second order approximation of the calculation. We use three points from the function to fit a second degree polynomial and calculate the surface beneath the figure. Simpson method has more precise solutions to problems.


### 4- Monte Carlo method:

This method is like the square integration method but $x_i$ is selected randomly (not uniform random mostly). This method can be used for non-continuous functions or functions with singularities.

Here is an example calculating some integral vs the points used in mc integration (N):

![download](https://github.com/mahyar-e/Numerical-Integration/assets/78594407/0649c64e-9479-435f-bd31-d1677814211f)

As you can see, the more points used, the better the calculated answer.

Also, you can see some exmaples solved using these method in the jupyter notebook.

Mohammad Mahyar Esfahani

