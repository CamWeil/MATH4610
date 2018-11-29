12a. **Routine Name:**           nmvecnorml1

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will compute and return the l<sub>1</sub> norm (length) of a given vector of arbitrary length.
   
   **Input:** There are inputs needed for the length of the vector and the elements of the vector. These inputs are both prompted for at the beginning of the routine.

   **Output:** This routine simply calculates the sum of the magnitude of each element of the vector, which is then given as the output.

   **Usage/Example:** The routine defines one double variable, l1, as well as an int variable, n, and a vector of with double elements, v. n represents the length of the vector, l1 represents the l<sub>1</sub> norm of the vector, and v represents the vector itself. The l<sub>1</sub> norm is calculated using the for loop:
   
        for(vector<double>::size_type i = 0; i < n; i++){
            l1 = l1 + fabs(v[i]);
        }

   **Implementation/Code:** The following is the code for nmvecnorml1.cpp:

        #include<iostream>
        #include<math.h>
        #include<vector>
        using namespace std;

        int n;
        double l1 = 0;

        int main(){
            cout << "Enter vector length: ";
            cin >> n;

            vector<double> v(n);

            for(vector<double>::size_type i = 0; i < n; i++){
                cout << "Enter coordinate #" << i + 1 << " for vector v: ";
                cin >> v[i];
            }

            for(vector<double>::size_type i = 0; i < n; i++){
                l1 = l1 + fabs(v[i]);
            }

            cout << "l1-norm = " << l1 << "." << endl;

            return 0;
        }

   **Last Modified:** November/2018
