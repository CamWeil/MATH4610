3. **Routine Name:**           nmabserr

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will absolute error between a machine precision number, x, and an "exact" value, y.

   **Input:** There are inputs needed for x and y.

   **Output:** This routine returns a double value of the absolute error e<sub>abs</sub> = |x - y|. 

   **Usage/Example:** The routine defines two float variables, eps and preveps, in which the value of the machine epsilon is found using the loop: 

        while((1+eps) != 1){
            preveps = eps;
            eps /= 2;
        }
            
   This defines the smallest number of eps such that 1 + eps is not equal to 1, which is then copied into preveps during each iteration. eps is divided by 2 in order to determine when the difference between 1 and the approximation is 0 in single precision, such that preveps is used as the output for the final machine epsilon when the approximation fails. This procedure is then repeated using double variables instead of float variables, and the output that each respective loop gives (in the author's case) is:

        Machine Epsilon (float) is : 1.19209e-07
        Machine Epsilon (double) is : 2.22045e-16
        Program ended with exit code: 0

   **Implementation/Code:** The following is the code for nmabserr.cpp:

        #include<iostream>
        #include<math.h>
        using namespace std;

        double x, y, abserr;

        int main(){
            cout << "Enter machine precision number x: ";
            cin >> x;
    
            cout << "Enter exact value y: ";
            cin >> y;
    
            abserr = fabs(x - y);
    
            cout << "Absolute Error: " << abserr << endl;
    
            return 0;
        }


        
   **Last Modified:** September/2018
