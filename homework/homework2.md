Homework 2

Note: I have yet to figure out how to allow the user to input a function in each routine, so the equations from the homework were hard-coded in.

1a. [Absolute Error Software Manual Entry](https://github.com/CamWeil/math4610/blob/master/softwaremanual/nmabserr.md)

1b. [Relative Error Software Manual Entry](https://github.com/CamWeil/math4610/blob/master/softwaremanual/nmrelerr.md)

2. 

3. 

4. [Functional Iteration Software Manual Entry](https://github.com/CamWeil/math4610/blob/master/softwaremanual/nmfunciter.md)

5. [Bisection Method Software Manual Entry](https://github.com/CamWeil/math4610/blob/master/softwaremanual/nmbisect.md)

6. [Newton's Method Software Manual Entry](https://github.com/CamWeil/math4610/blob/master/softwaremanual/nmnewton.md)

7. [Secant Method Software Manual Entry](https://github.com/CamWeil/math4610/blob/master/softwaremanual/nmsecant.md)

8. [Hybrid Method Software Manual Entry (Bisection and Newton)](https://github.com/CamWeil/math4610/blob/master/softwaremanual/nmhybridbn.md)

9. [Hybrid Method Software Manual Entry (Bisection and Secant)](https://github.com/CamWeil/math4610/blob/master/softwaremanual/nmhybridbs.md)

10. Problem: Perform an online search for references to bracketing of roots of functions of a single real variable. Look for applications and explanations of how to bracket roots of nonlinear functions. Make sure that you cite at least three sources. You can cite websites and/or web pages that discuss bracketing.

    Answer: One example of a nonlinear equation that can be solved using root bracketing methods originates from one of Kepler's laws of planetary motion. Kepler's equation, which can be used to determine the position of an object in an elliptical orbit, is given by M = E - esin(E). Since the inverse Kepler equation does not have a closed-form solution, it is considerably more difficult to solve for E when M is given as opposed to M when E is given. As such, iteratively finding the root of the function f(E) = E - e sin(E) - M(t) is one way to go about this. While Newton's method can be used for fast convergence, given E<sub>n+1</sub> = E<sub>n</sub> - f(E<sub>n</sub>)/f'(E<sub>n</sub>) = E<sub>n</sub> - (E<sub>n</sub> - e sin(E<sub>n</sub>) - M(t))/(1 - e cos(E<sub>n</sub>)), the bisection method can also be used as a simpler approach, as well as hybrid methods utilizing bisection, where the interval is determined based on the value of e, given E = M + e and E = M - e as the bracketing points. The bisection method is also more stable overall for high values of e. 

    Sources: Kepler's equation. (2018, August 11). Retrieved September 30, 2018, from https://en.wikipedia.org/wiki/Kepler%27s_equation
             Kepler’s Equation of Elliptical Motion Solver. (2012, April 07). Retrieved September 30, 2018, from https://binnerd.blogspot.com/2012/04/elliptical-motion-solver.html
             Kepler's equation and the Equation of Centre. (1998, November 01). Retrieved September 20, 2018, from http://www.stargazing.net/kepler/kepler.html#twig02
    
