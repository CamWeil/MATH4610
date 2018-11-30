14d. **Routine Name:**           nmvecopsdot

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will compute and return the inner product of two vectors of equal length (v1 • v2).
   
   **Input:** There are inputs needed for the length of the two vectors and the elements of the two vectors. These inputs are all prompted for at the beginning of the routine.

   **Output:** This routine simply calculates the inner product of two vectors, which is then given as the output. For example:
   
        Enter vector length: 3
        Enter coordinate #1 for vector v1: 1
        Enter coordinate #2 for vector v1: 2
        Enter coordinate #3 for vector v1: 3
        Enter coordinate #1 for vector v2: 4
        Enter coordinate #2 for vector v2: 5
        Enter coordinate #3 for vector v2: 6
        v1 • v2 = 32.

   **Usage/Example:** The routine defines one int variable, n, and a double variable v3d, as well as two vectors with double elements, v1 and v2. n represents the length of the two vectors, v3d represents the inner product of the two vectors, and v1 and v2 represent the vectors themselves. The value of v3d is calculated using the loop:
   
        for(vector<double>::size_type i = 0; i < n; i++){
            v3d = v3d + v1[i]*v2[i];
        }

   **Implementation/Code:** The following is the code for nmvecopsdot.cpp:

        #include<iostream>
        #include<math.h>
        #include<vector>
        using namespace std;

        int n;

        int main(){
            cout << "Enter vector length: ";
            cin >> n;

            vector<double> v1(n);
            vector<double> v2(n);
            double v3d = 0;

            for(vector<double>::size_type i = 0; i < n; i++){
                cout << "Enter coordinate #" << i + 1 << " for vector v1: ";
                cin >> v1[i];
            }

            for(vector<double>::size_type i = 0; i < n; i++){
                cout << "Enter coordinate #" << i + 1 << " for vector v2: ";
                cin >> v2[i];
            }

            cout << "v1 • v2 = ";

            for(vector<double>::size_type i = 0; i < n; i++){
                v3d = v3d + v1[i]*v2[i];
            }

            cout << v3d << "." << endl;

            return 0;
        }

   **Last Modified:** November/2018
