14c. **Routine Name:**           nmvecopsmultsc

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will compute and return the product of a scalar and a vector (c * v1).
   
   **Input:** There are inputs needed for the length of the vector, the elements of the vector, and the value of the scalar. These inputs are all prompted for at the beginning of the routine.

   **Output:** This routine simply calculates the product of a scalar and a vector by multiplying each respective element of the vector by the scalar, which is then given as the output. For example:
   
        Enter vector length: 3
        Enter scalar c: 3
        Enter coordinate #1 for vector v1: 1
        Enter coordinate #2 for vector v1: 2
        Enter coordinate #3 for vector v1: 3
        c * v1 = < 3  6  9 >.

   **Usage/Example:** The routine defines one int variable, n, and a double variable, c, as well as two vectors with double elements, v1, and v3c. n represents the length of the two vectors, c represents the scalar, v3c represents the product between the scalar and the vector, and v1 represents the vector itself. The value of v3c is calculated using the loop:
   
        for(vector<double>::size_type i = 0; i < n; i++){
            v3c[i] = c*v1[i];
        }

   **Implementation/Code:** The following is the code for nmvecopsmultsc.cpp:

        #include<iostream>
        #include<math.h>
        #include<vector>
        using namespace std;

        int n;
        double c;

        int main(){
            cout << "Enter vector length: ";
            cin >> n;

            cout << "Enter scalar c: ";
            cin >> c;

            vector<double> v1(n);
            vector<double> v3c(n);

            for(vector<double>::size_type i = 0; i < n; i++){
                cout << "Enter coordinate #" << i + 1 << " for vector v1: ";
                cin >> v1[i];
            }

            cout << "c * v1 = <";

            for(vector<double>::size_type i = 0; i < n; i++){
                v3c[i] = c*v1[i];
                cout << " " << v3c[i] << " ";
            }

            cout << ">." << endl;

            return 0;
        }

   **Last Modified:** November/2018
