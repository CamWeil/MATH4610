06. **Routine Name:**           nmnewton

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will implement Newton's method of root solving for the equations f(x) = x<sup>2</sup> - 3 and f(x) = sin(pi*x).

   **Input:** There are inputs needed for p0 as an initial estimate, tol for the tolerated level of error, and maxiter for the maximum number of iterations. These inputs are all prompted for at the beginning of the routine.

   **Output:** This routine returns a root that exists near enough to the inputted intial estimate using a given function f(x) and its derivative, f'(x). For example, the inputs p0 = 1, tol = 0.001, and maxiter = 100 for the equations f(x) = x<sup>2</sup> - 3, f'(x) = 2x will return the output:
  
        Iteration 1: x = 2
        Iteration 2: x = 1.75
        Iteration 3: x = 1.73214
        Iteration 4: x = 1.73205
        The approximated root of x^2 - 3 = 0 is x = 1.73205.

   **Usage/Example:** The routine defines three double variables, p, p0, and tol, as well as two int variables, i and maxiter. p0 represent an initial estimate for the root of a function, and p is used to redefine p0 at the end of every iteration. tol indicates how close the value of p must be during a given iteration to be taken as a satisfactory solution. If the loop surpasses the value inputted by maxiter, then the algorithm will fail. It is also worth noting that the code contains algorithms for both f(x) = x<sup>2</sup> - 3 and f(x) = sin(pi*x), but the two should not be run at the same time. Thus, one equation or another can be commented out depending on which algorithm the user wants to work with at any given moment.

   **Implementation/Code:** The following is the code for nmnewton.cpp:

        #include<iostream>
        #include<math.h>
        using namespace std;

        double p, p0, tol;
        int i = 1, maxiter;

        double f1(double x){
            return x*x - 3;
        }

        double df1(double x){
            return 2*x;
        }

        double f2(double x){
            return sin(M_PI*x);
        }

        double df2(double x){
            return M_PI*cos(M_PI*x);
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
    
            cout << "Enter an initial estimate: ";
            cin >> p0;
    
            // code for x^2 - 3 = 0
    
            while(i <= maxiter){
                p = p0 - (f1(p0))/(df1(p0));
                cout << "Iteration " << i << ": x = " << p << endl;
        
                if(fabs(p - p0) < tol){
                    cout << "The approximated root of x^2 - 3 = 0 is x = " << p << "." << endl;
                    break;
                }
        
                i++;
                p0 = p;
        
              if(i > maxiter){
                    cout << "Root not found." << endl;
                    break;
              }
        
            }
    
            // code for sin(pi*x) = 0
    
            /*while(i <= maxiter){
                p = p0 - (f2(p0))/(df2(p0));
                cout << "Iteration " << i << ": x = " << p << endl;
     
                if(fabs(p - p0) < tol){
                    cout << "The approximated root of sin(pi*x) = 0 is x = " << p << "." << endl;
                    break;
                }
     
                i++;
                p0 = p;
     
                if(i > maxiter){
                    cout << "Root not found." << endl;
                    break;
                }
     
            }*/
    
            return 0;
        }
 
   **Last Modified:** November/2018
