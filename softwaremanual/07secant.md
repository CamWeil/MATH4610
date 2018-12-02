07. **Routine Name:**           nmsecant

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will implement the secant method of root solving for the equations f(x) = x<sup>2</sup> - 3 and f(x) = sin(pi*x).

   **Input:** There are inputs needed for p0 and p1 as initial estimates, tol for the tolerated level of error, and maxiter for the maximum number of iterations. These inputs are all prompted for at the beginning of the routine.

   **Output:** This routine returns a root using a given function f(x) evaluated sequentially at both initial estimates. For example, the inputs p0 = 1, tol = 0.001, and maxiter = 100 for the equation f(x) = x<sup>2</sup> - 3 will return the output:
  
        Iteration 1: x = 1.66667
        Iteration 2: x = 1.72727
        Iteration 3: x = 1.73214
        Iteration 4: x = 1.73205
        The approximated root of x^2 - 3 = 0 is x = 1.73205.

   **Usage/Example:** The routine defines four double variables, p, p0, p1, and tol, as well as two int variables, i and maxiter. p0 and p1 represent two initial estimates for the root of a function, and p is used to redefine p0 and p1 at the end of every iteration, as such:
   
        p0 = p1;
        p1 = p;
   
   tol indicates how close the value of p must be during a given iteration to be taken as a satisfactory solution. If the loop surpasses the value inputted by maxiter, then the algorithm will fail. It is also worth noting that the code contains algorithms for both f(x) = x<sup>2</sup> - 3 and f(x) = sin(pi*x), but the two should not be run at the same time. Thus, one equation or another can be commented out depending on which algorithm the user wants to work with at any given moment.

   **Implementation/Code:** The following is the code for nmsecant.cpp:

        #include<iostream>
        #include<math.h>
        using namespace std;

        double p, p0, p1, tol;
        int i = 1, maxiter;

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
    
            cout << "Enter an initial estimate: ";
            cin >> p0;
    
            cout << "Enter another initial estimate: ";
            cin >> p1;
    
            if (p1 == p0){
                cout << "Initial estimates cannot be the same. Enter another initial estimate: ";
                cin >> p1;
            }
    
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
                    cout << "Root not found." << endl;
                    break;
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
                    cout << "Root not found." << endl;
                    break;
                }
        
            }*/
    
            return 0;
        }
 
   **Last Modified:** November/2018
