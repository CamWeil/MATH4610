03a. **Routine Name:**           nmabserr

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will calculate the absolute error between a machine precision number, x, and an "exact" value, y.

   **Input:** There are inputs needed for x and y. These inputs are prompted for at the beginning of the routine.

   **Output:** This routine returns the absolute error, e<sub>abs</sub> = |x - y|. For example, the inputs x = 1 and y = 2 will return the output:

        Absolute Error: 1

   **Usage/Example:** The routine defines a double variable, abserr, which is defined as:

        abserr = fabs(x - y);
            
   This is simply used to calculate the magnitude of difference between the inputted values of x and y.

   **Implementation/Code:** The following is the code for nmabserr.cpp:

        #include<iostream>
        #include<math.h>
        using namespace std;

        double x, y, abserr;

        int main(){
            cout << "Enter machine precision number x: ";
            cin >> x;
            
            if(x == 0){
                cout << "x cannot be 0. Enter machine precision number x: ";
                cin >> x;
            }
    
            cout << "Enter exact value y: ";
            cin >> y;
    
            abserr = fabs(x - y);
    
            cout << "Absolute Error: " << abserr << endl;
    
            return 0;
        }
        
   **Last Modified:** November/2018
