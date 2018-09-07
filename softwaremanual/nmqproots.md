1. **Routine Name:**           nmqproots

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will compute the roots of a quadratic polynomial. This is a routine for solving any polynomial of the form ax^2 + bx + c so long as a ≠ 0.

   **Input:** There are inputs needed for a, b, and c.

   **Output:** This routine returns the two roots of the solution x = (-b ± \sqrt{b^2 - 4ac})/2a.

   **Usage/Example:** The routine defines two float variables, eps and preveps, in which the value of the machine epsilon is found using the loop: 

         while((1+eps) != 1){
             preveps = eps;
             eps /= 2;
         }
            
   This defines the smallest number of eps such that 1 + eps is not equal to 1, which is then copied into preveps during each iteration. eps is divided by 2 in order to determine when the difference between 1 and the approximation is 0 in single precision, such that preveps is used as the output for the final machine epsilon when the approximation fails. This procedure is then repeated using double variables instead of float variables, and the output that each respective loop gives (in the author's case) is:

        Machine Epsilon (float) is : 1.19209e-07
        Machine Epsilon (double) is : 2.22045e-16
        Program ended with exit code: 0

   **Implementation/Code:** The following is the code for nmmaceps.cpp:

        #include<iostream>
        #include<cfloat>
        using namespace std;

        void nmmaceps(float eps){
            float preveps;
    
            while((1+eps) != 1){
                preveps = eps;
                eps /= 2;
            }
    
            cout << "Machine Epsilon (float) is : " << preveps << endl;
        }

        void nmdmaceps(double deps){
            double prevdeps;
    
            while((1+deps) != 1){
                prevdeps = deps;
                deps /= 2;
            }
    
            cout << "Machine Epsilon (double) is : " << prevdeps << endl;
        }

        int main(){
            nmmaceps(0.5);
            nmdmaceps(0.5);
    
            return 0;
        }

        
   **Last Modified:** September/2018
