3. **Routine Name:**           nmbisect

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will implement the bisection method of root solving for the equations f(x) = x<sup>2</sup> - 3 and f(x) = sin(pix).

   **Input:** There are inputs needed for a and b to bracket a root, tol for the tolerated level of error, and maxiter for the maximum number of iterations. These inputs are all prompted for at the beginning of the routine.

   **Output:** This routine returns any root that exists between the inputted values of a and b. For example, the inputs a = 1, b = 2, tol = 0.001, and maxiter = 1000 for the equation f(x) = x<sup>2</sup> - 3 will return the output:
  
        Iteration 0: x = 1.5
        Iteration 1: x = 1.75
        Iteration 2: x = 1.625
        Iteration 3: x = 1.6875
        Iteration 4: x = 1.71875
        Iteration 5: x = 1.73438
        Iteration 6: x = 1.72656
        Iteration 7: x = 1.73047
        Iteration 8: x = 1.73242
        The approximated root of x^2 - 3 = 0 is x = 1.73242.

   **Usage/Example:** The routine defines eight float variables, a, b, c, x1, x2, disc, xreal, and ximag. a, b, and c are the coefficients of the polynomial and disc is the discriminant of the polynomial, which is given as:

        disc = b*b - 4*a*c;
   
   The value of the discriminant is used to determine how the roots of the polynomial should be calculated. If the discriminant is positive or zero, then the roots are real and are given as:
   
        x1 = (-b + sqrt(disc))/(2*a);
        x2 = (-b - sqrt(disc))/(2*a);
        
   If the discriminant is negative, then the roots are complex and are given as:
   
        xreal = -b/(2*a);
        ximag = sqrt(-disc)/(2*a);

  This is necessary to ensure that the routine never has to take the square root of a negative number, which would otherwise return an undefined value. It is also worth noting that if the discriminant is zero, then x1 and x2 will return identical values.

   **Implementation/Code:** The following is the code for nmqproots.cpp:

        #include<iostream>
        #include<math.h>
        using namespace std;

        int main(){

        float a, b, c, x1, x2, disc, xreal, ximag;

            cout << "Enter coefficient a: ";
            cin >> a;
    
                if(a == 0){
                    cout << "a cannot be 0. Enter coefficient a: ";
                    cin >> a;
                }
    
            cout << "Enter coefficient b: ";
            cin >> b;
            cout << "Enter coefficient c: ";
            cin >> c;
    
            disc = b*b - 4*a*c;
    
                if(disc >= 0){
                    x1 = (-b + sqrt(disc))/(2*a);
                    x2 = (-b - sqrt(disc))/(2*a);
                    cout << "x1 = " << x1 << endl;
                    cout << "x2 = " << x2 << endl;
                }
    
                else{
                    xreal = -b/(2*a);
                    ximag = sqrt(-disc)/(2*a);
                    cout << "x1 = " << xreal << " + " << ximag << "i" << endl;
                    cout << "x2 = " << xreal << " - " << ximag << "i" << endl;
                }

            return 0;
    
        }
        
   **Last Modified:** September/2018