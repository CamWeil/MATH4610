1a. **Routine Name:**           nmmaceps

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will compute the single precision values for the machine epsilon or the number of digits in the representation of real numbers in single precision. This is a routine for analyzing the behavior of any computer. This usually will need to be run one time for each computer.

   **Input:** There are no inputs needed in this case. Even though there are arguments supplied, the real purpose is to return values in those variables.

   **Output:** This routine returns a single precision value for the number of decimal digits that can be represented on the computer being queried.

   **Usage/Example:** The routine defines two float variables, eps and preveps, in which the value of the machine epsilon is found using the loop: 

        while((1+eps) != 1){
            preveps = eps;
            eps /= 2;
        }
            
   This defines the smallest number of eps such that 1 + eps is not equal to 1, which is then copied into preveps during each iteration. eps is divided by 2 in order to determine when the difference between 1 and the approximation is 0 in single precision, such that preveps is used as the output for the final machine epsilon when the approximation fails. The outpute that the loop gives is:

        Machine Epsilon (float) is : 1.19209e-07
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

        int main(){
            nmmaceps(0.5);
    
            return 0;
        }

        
   **Last Modified:** September/2018
