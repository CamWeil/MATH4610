01b. **Routine Name:**           nmdmaceps

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will compute the double precision values for the machine epsilon or the number of digits in the representation of real numbers in double precision. This is a routine for analyzing the behavior of any computer. This usually will need to be run one time for each computer.

   **Input:** There are no inputs needed in this case. Even though there are arguments supplied, the real purpose is to return values in those variables.

   **Output:** This routine returns a double precision value for the number of decimal digits that can be represented on the computer being queried.

   **Usage/Example:** The routine defines two double variables, eps and preveps, in which the value of the machine epsilon is found using the loop: 

        while((1+eps) != 1){
            preveps = eps;
            eps /= 2;
        }
            
   This defines the smallest number of eps such that 1 + eps is not equal to 1, which is then copied into preveps during each iteration. eps is divided by 2 in order to determine when the difference between 1 and the approximation is 0 in double precision, such that preveps is used as the output for the final machine epsilon when the approximation fails. The output that the loop gives is:

        Machine Epsilon (double) is : 2.22045e-16
        Program ended with exit code: 0

   **Implementation/Code:** The following is the code for nmdmaceps.cpp:

        #include<iostream>
        #include<cfloat>
        using namespace std;

        void nmdmaceps(double deps){
            double prevdeps;
    
            while((1+deps) != 1){
                prevdeps = deps;
                deps /= 2;
            }
    
            cout << "Machine Epsilon (double) is : " << prevdeps << endl;
        }

        int main(){
            nmdmaceps(0.5);
    
            return 0;
        }

        
   **Last Modified:** November/2018
