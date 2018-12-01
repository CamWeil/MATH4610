03b. **Routine Name:**           nmrelerr

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will calculate the relative error between a machine precision number, x, and an "exact" value, y.

   **Input:** There are inputs needed for x and y. These inputs are prompted for at the beginning of the routine.

   **Output:** This routine returns the relative error, e<sub>rel</sub> = |x - y|/x. For example, the inputs x = 1 and y = 2 will return the output:

        Relative Error: 1

   **Usage/Example:** The routine defines a double variable, relerr, which is defined as:

        relerr = (fabs(x - y))/x;
            
   This is simply used to calculate the magnitude of difference between the inputted values of x and y with respect to the relative value x.

   **Implementation/Code:** The following is the code for nmabserr.cpp:

        #include<iostream>
        #include<math.h>
        using namespace std;

        double x, y, relerr;

        int main(){
            cout << "Enter machine precision number x: ";
            cin >> x;
    
            if(x == 0){
                cout << "x cannot be 0. Enter machine precision number x: ";
                cin >> x;
            }
    
            cout << "Enter exact value y: ";
            cin >> y;
    
            relerr = (fabs(x - y))/x;

            cout << "Relative Error: " << relerr << endl;
    
            return 0;
        }

   **Last Modified:** November/2018
