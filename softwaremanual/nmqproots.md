1. **Routine Name:**           nmqproots

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will compute the roots of a quadratic polynomial. This is a routine for solving any polynomial of the form ax^2 + bx + c so long as a ≠ 0.

   **Input:** There are inputs needed for a, b, and c.

   **Output:** This routine returns the two roots to the solution: 
   
      <img src="https://latex.codecogs.com/svg.latex?\Large&space;x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}" title="\Large x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}" />

   **Usage/Example:** The routine defines eight float variables, a, b, c, x1, x2, disc, xreal, and ximag.  

         while((1+eps) != 1){
             preveps = eps;
             eps /= 2;
         }
            
   This defines the smallest number of eps such that 1 + eps is not equal to 1, which is then copied into preveps during each iteration. eps is divided by 2 in order to determine when the difference between 1 and the approximation is 0 in single precision, such that preveps is used as the output for the final machine epsilon when the approximation fails. This procedure is then repeated using double variables instead of float variables, and the output that each respective loop gives (in the author's case) is:

        Machine Epsilon (float) is : 1.19209e-07
        Machine Epsilon (double) is : 2.22045e-16
        Program ended with exit code: 0

   **Implementation/Code:** The following is the code for nmqproots.cpp:

        #include<iostream>
        #include<iomanip>
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
    
        };
        
   **Last Modified:** September/2018