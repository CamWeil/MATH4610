9. **Routine Name:**           nmhybridbs

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will implement a hybrid method of root solving using both bisection and the secant method for the equations f(x) = x<sup>2</sup> - 3 and f(x) = sin(pi*x).

   **Input:** There are inputs needed for a and b to bracket a root, tol for the tolerated level of error, and maxiter for the maximum number of iterations. These inputs are all prompted for at the beginning of the routine.

   **Output:** This routine first attempts to find a root using the secant method. If this fails, the routine will implement four steps of the bisection method to ensure that a root is bracketed, and then return to the secant method to complete the algorithm. For example, the inputs a = 1, b = 10, tol = 0.001, and maxiter = 3 for the equation f(x) = x<sup>2</sup> - 3 will return the output:
  
        Iteration 1: x = 1.18182
        Iteration 2: x = 1.3252
        Iteration 3: x = 1.82134
        Root not found. Implementing bisection method.
        Iteration 4: x = 5.5
        Iteration 5: x = 3.25
        Iteration 6: x = 2.125
        Iteration 7: x = 1.5625
        Root bracketed. Implementing secant method. 
        Iteration 8: x = 1.72758
        Iteration 9: x = 1.73228
        Iteration 10: x = 1.73205
        The approximated root of x^2 - 3 = 0 is x = 1.73205.

   **Usage/Example:** The routine defines ten double variables, a, b, c, fa, fb, fc, p, p0, p1, and tol, as well as four int variables, i, j, k, and maxiter. a and b represent the ends of an interval where f(x) is known to change sign, and fa and fb are f(a) and f(b) respectively. c is the midpoint between a and b during a given iteration, and fc is f(c). p0 and p1 are initially chosen as a and b, and p is used to redefine p0 and p1 at the end of every iteration, as such:
   
        p0 = p1;
        p1 = p;
   
   However, after the bisection method has taken place, p1 is given by c so as to continue the secant method with a better approximation, as such:
   
        p0 = p1;
        p1 = c;
   
   tol indicates how close the value of c must be during a given iteration to be taken as a satisfactory solution. If the loop surpasses the value inputted by maxiter, then the algorithm will fail. i, j, and k are values used for the various loops in each portion of the routine. It is also worth noting that the code contains algorithms for both f(x) = x<sup>2</sup> - 3 and f(x) = sin(pi*x), but the two should not be run at the same time. Thus, one equation or another can be commented out depending on which algorithm the user wants to work with at any given moment.

   **Implementation/Code:** The following is the code for nmhybridbs.cpp:

        #include<iostream>
        #include<math.h>
        using namespace std;

        double a, b, c, fa, fb, fc, p, p0, p1, tol;
        int i = 1, j, k = 1, maxiter;

        double f1(double x){
            return x*x - 3;
        }

        double f2(double x){
            return sin(M_PI*x);
        }

        int main(){
            cout << "Enter tolerance level: ";
            cin >> tol;

            if(tol == 0){
                cout << "Tolerance level cannot be 0. Enter tolerance level: ";
                cin >> tol;
            }

            cout << "Enter maximum number of iterations: ";
            cin >> maxiter;

            if(maxiter == 0){
                cout << "Maximum number of iterations cannot be 0. Enter maximum number of iterations: ";
                cin >> maxiter;
            }

            cout << "Enter boundary a: ";
            cin >> a;

            cout << "Enter boundary b: ";
            cin >> b;

            if (b == a){
                cout << "a cannot equal b. Enter boundary b: ";
                cin >> b;
            }

            p0 = a;
            p1 = b;

            // code for x^2 - 3 = 0

            while(i <= maxiter){
                p = p1 - ((f1(p1))*(p1 - p0))/(f1(p1) - f1(p0));
                cout << "Iteration " << i << ": x = " << p << endl;

                if(fabs(p - p1) < tol){
                    cout << "The approximated root of x^2 - 3 = 0 is x = " << p << "." << endl;
                    break;
                }

                i++;
                p0 = p1;
                p1 = p;

                    if(i > maxiter){
                    cout << "Root not found. Implementing bisection method." << endl;

                    fa = f1(a);
                    fb = f1(b);

                    if(fa*fb >= 0){
                        cout << "Error. a and b do not bracket any root." << endl;
                        break;
                    }

                    else{
                        for(j = 1; j <= 4; j++){
                            c = 0.5*(a + b);
                            fc = f1(c);

                            if(fa*fc < 0){
                                b = c;
                                fb = fc;
                            }

                            else{
                                a = c;
                                fa = fc;
                            }

                            cout << "Iteration " << i + j - 1 << ": x = " << c << endl;
                        }
                    }

                    p0 = p1;
                    p1 = c;

                    cout << "Root bracketed. Implementing secant method. " << endl;

                    while(k <= maxiter){
                        p = p1 - ((f1(p1))*(p1 - p0))/(f1(p1) - f1(p0));
                        cout << "Iteration " << i + j + k - 2 << ": x = " << p << endl;

                        if(fabs(p - p1) < tol){
                            cout << "The approximated root of x^2 - 3 = 0 is x = " << p << "." << endl;
                            break;
                        }

                        k++;
                        p0 = p1;
                        p1 = p;

                        if(k > maxiter){
                            cout << "Root not found." << endl;
                            break;
                        }

                    }
                }
            }

            // code for sin(pi*x) = 0

            /*while(i <= maxiter){
                p = p1 - ((f2(p1))*(p1 - p0))/(f2(p1) - f2(p0));
                cout << "Iteration " << i << ": x = " << p << endl;

                if(fabs(p - p1) < tol){
                    cout << "The approximated root of sin(pi*x) = 0 is x = " << p << "." << endl;
                    break;
                }

                i++;
                p0 = p1;
                p1 = p;

                if(i > maxiter){
                    cout << "Root not found. Implementing bisection method." << endl;

                    fa = f2(a);
                    fb = f2(b);

                    if(fa*fb >= 0){
                        cout << "Error. a and b do not bracket any root." << endl;
                        break;
                    }

                    else{
                        for(j = 1; j <= 4; j++){
                            c = 0.5*(a + b);
                            fc = f2(c);

                            if(fa*fc < 0){
                                b = c;
                                fb = fc;
                            }

                            else{
                                a = c;
                                fa = fc;
                            }

                            cout << "Iteration " << i + j - 1 << ": x = " << c << endl;
                        }
                    }

                    p0 = p1;
                    p1 = c;

                    cout << "Root bracketed. Implementing secant method. " << endl;

                    while(k <= maxiter){
                        p = p1 - ((f2(p1))*(p1 - p0))/(f2(p1) - f2(p0));
                        cout << "Iteration " << i + j + k - 2 << ": x = " << p << endl;

                        if(fabs(p - p1) < tol){
                            cout << "The approximated root of sin(pi*x) = 0 is x = " << p << "." << endl;
                            break;
                        }

                        k++;
                        p0 = p1;
                        p1 = p;

                        if(k > maxiter){
                            cout << "Root not found." << endl;
                            break;
                        }

                    }
                }
            }*/

            return 0;
        }

   **Last Modified:** September/2018
