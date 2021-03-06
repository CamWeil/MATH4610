05. **Routine Name:**           nmbisect

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will implement the bisection method of root solving for the equations f(x) = x<sup>2</sup> - 3 and f(x) = sin(pi*x).

   **Input:** There are inputs needed for a and b to bracket a root, and tol for the tolerated level of error. These inputs are all prompted for at the beginning of the routine.

   **Output:** This routine returns any root that exists between the inputted values of a and b. For example, the inputs a = 1, b = 2, and tol = 0.001 for the equation f(x) = x<sup>2</sup> - 3 will return the output:
  
        Iteration 1: x = 1.5
        Iteration 2: x = 1.75
        Iteration 3: x = 1.625
        Iteration 4: x = 1.6875
        Iteration 5: x = 1.71875
        Iteration 6: x = 1.73438
        Iteration 7: x = 1.72656
        Iteration 8: x = 1.73047
        The approximated root of x^2 - 3 = 0 is x = 1.73047.

   **Usage/Example:** The routine defines eight double variables, a, b, c, fa, fb, fc, k, and tol, as well as one int variable, i. a and b represent the ends of an interval where f(x) is known to change sign, and fa and fb are f(a) and f(b) respectively. c is the midpoint between a and b during a given iteration, and fc is f(c). tol indicates how close the value of c must be during a given iteration to be taken as a satisfactory solution. k is a value that guarantees the convergence of the algorithm, which is given as:

        k = log2(fabs(b - a)/(2*tol));
   
   So long as i < k, the iteration loop will continue until a root is found. If the loop surpasses the value inputted by maxiter, then the algorithm will fail. It is also worth noting that the code contains algorithms for both f(x) = x<sup>2</sup> - 3 and f(x) = sin(pi*x), but the two should not be run at the same time. Thus, one equation or another can be commented out depending on which algorithm the user wants to work with at any given moment.

   **Implementation/Code:** The following is the code for nmbisect.cpp:

        #include<iostream>
        #include<math.h>
        using namespace std;

        double a, b, c, fa, fb, fc, k, tol;
        int i;

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
    
            cout << "Enter boundary a: ";
            cin >> a;
    
            cout << "Enter boundary b: ";
            cin >> b;
    
            if (b == a){
                cout << "a cannot equal b. Enter boundary b: ";
                cin >> b;
            }
    
            // code for x^2 - 3 = 0
    
            fa = f1(a);
            fb = f1(b);
    
            if(fa*fb >= 0){
                cout << "Error. a and b do not bracket any root." << endl;
            }
    
            else{
                k = log2(fabs(b - a)/(2*tol));
        
                for(i = 1; i <= k; i++){
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
                    
                    cout << "Iteration " << i << ": x = " << c << endl;
        
                }
        
                cout << "The approximated root of x^2 - 3 = 0 is x = " << c << "." << endl;
            }
    
            // code for sin(pi*x) = 0
    
            /*fa = f2(a);
            fb = f2(b);
    
            if(fa*fb >= 0){
                cout << "Error. a and b do not bracket any root." << endl;
            }
    
            else{
                k = log2(fabs(b - a)/(2*tol));
        
                for(i = 1; i <= k; i++){
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
                    
                    cout << "Iteration " << i << ": x = " << c << endl;
            
                }
        
                cout << "The approximated root of sin(pi*x) = 0 is x = " << c << "." << endl;
            }*/
    
            return 0;
        }
        
   **Last Modified:** November/2018
   
