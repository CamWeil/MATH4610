Homework 1

1. [Machine Epsilon Software Manual Entry](https://github.com/CamWeil/math4610/blob/master/softwaremanual/nmmaceps.md)

2. [Quadratic Polynomial Roots Software Manual Entry](https://github.com/CamWeil/math4610/blob/master/softwaremanual/nmqproots.md)

3. [Calculus/Differential Equations Solutions](https://github.com/CamWeil/math4610/blob/master/homework/nmhw1.pdf)

4. Problem: Search the internet for an application that is influenced by machine precision. Write a paragraph on one of the results you have found. Identify one and only one such web site. Make sure that you cite the web site appropriately.

   Answer: Machine precision is an influential factor in the application of floating-point arithmetic, which is used to represent real numbers that are either very large or very small and require fast processing times. As floating-point computations are approximated using a fixed number of significant digits such that some precision is sacrificed for higher efficiency, machine epsilon is an important quantity in the backwards error analysis of floating-point algorithms. This method determines the accuracy of a floating-point system by bounding the relative error of any non-zero real number that is being represented, which can be used to establish the numerical stability of an algorithm. If the roundoff error is small enough to where the result of a floating-point function is an exact solution to a similar problem with slightly perturbed input data, then the algorithm can be deemed "backward stable", which indicates that any accuracy errors are on the order of the uncertainty in the input data.

   Source: Floating-point arithmetic. (2018, September 06). Retrieved September 6, 2018, from https://en.wikipedia.org/wiki/Floating-point_arithmetic
