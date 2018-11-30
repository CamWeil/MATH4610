14a. **Routine Name:**           nmvecopsadd

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will compute and return the sum of two vectors of equal length (v1 + v2).
   
   **Input:** There are inputs needed for the length of the two vectors and the elements of the two vectors. These inputs are all prompted for at the beginning of the routine.

   **Output:** This routine simply calculates the sum of two vectors by adding each respective element together, which is then given as the output. For example:
   
        Enter vector length: 3
        Enter coordinate #1 for vector v1: 1
        Enter coordinate #2 for vector v1: 2
        Enter coordinate #3 for vector v1: 3
        Enter coordinate #1 for vector v2: 4
        Enter coordinate #2 for vector v2: 5
        Enter coordinate #3 for vector v2: 6
        v1 + v2 = < 5  7  9 >.

   **Usage/Example:** The routine defines one int variable, n, as well as three vectors with double elements, v1, v2, and v3a. n represents the length of the two vectors, v3a represents the sum of the two vectors, and v1 and v2 represent the vectors themselves. The value of v3a is calculated using the loop:
   
        for(vector<double>::size_type i = 0; i < n; i++){
            v3a[i] = v1[i] + v2[i];
        }

   **Implementation/Code:** The following is the code for nmvecopsadd.cpp:

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
            vector<double> v3a(n);

            for(vector<double>::size_type i = 0; i < n; i++){
                cout << "Enter coordinate #" << i + 1 << " for vector v1: ";
                cin >> v1[i];
            }

            for(vector<double>::size_type i = 0; i < n; i++){
                cout << "Enter coordinate #" << i + 1 << " for vector v2: ";
                cin >> v2[i];
            }

            cout << "v1 + v2 = <";

            for(vector<double>::size_type i = 0; i < n; i++){
                v3a[i] = v1[i] + v2[i];
                cout << " " << v3a[i] << " ";
            }

            cout << ">." << endl;

            return 0;
        }

   **Last Modified:** November/2018
