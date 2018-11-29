13a. **Routine Name:**           nmvecerrl1

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will compute and return the absolute and relative errors of the l<sub>1</sub> norm (length) of an "exact" vector and a vector used to approximate the exact vector.
   
   **Input:** There are inputs needed for the length of the two vectors and the elements of the exact vector and the approximate vector. These inputs are all prompted for at the beginning of the routine.

   **Output:** This routine simply calculates the sum of the magnitude of each element of both the exact vector and the approximate vector, and then the absolute and relative errors of these sums, which is given as the output. For example:
   
        Enter vector length: 3
        Enter coordinate #1 for approximate vector x: 1
        Enter coordinate #2 for approximate vector x: 2
        Enter coordinate #3 for approximate vector x: 3
        Enter coordinate #1 for exact vector y: 2
        Enter coordinate #2 for exact vector y: 3
        Enter coordinate #3 for exact vector y: 4
        l1-norm error (absolute) = 3.
        l1-norm error (relative) = 0.5.

   **Usage/Example:** The routine defines two double variables, l1x and l1y, as well as an int variable, n, and two vectors with double elements, x and y. n represents the length of the two vectors, l1x represents the l<sub>1</sub> norm of the approximate vector and l1y represents the l<sub>1</sub> norm of the exact vector, and x and y represent the approximate vector and the exact vector, respectively. The l<sub>1</sub> norms of the two vectors are calculated using the loop:
   
        for(vector<double>::size_type i = 0; i < n; i++){
            l1x = l1x + fabs(x[i]);
            l1y = l1y + fabs(y[i]);
        }

   **Implementation/Code:** The following is the code for nmvecerrl1.cpp:

        #include<iostream>
        #include<math.h>
        #include<vector>
        using namespace std;

        int n;
        double l1x = 0;
        double l1y = 0;

        int main(){
            cout << "Enter vector length: ";
            cin >> n;

            vector<double> x(n);
            vector<double> y(n);

            for(vector<double>::size_type i = 0; i < n; i++){
                cout << "Enter coordinate #" << i + 1 << " for approximate vector x: ";
                cin >> x[i];
            }

            for(vector<double>::size_type i = 0; i < n; i++){
                cout << "Enter coordinate #" << i + 1 << " for exact vector y: ";
                cin >> y[i];
            }

            for(vector<double>::size_type i = 0; i < n; i++){
                l1x = l1x + fabs(x[i]);
                l1y = l1y + fabs(y[i]);
            }

            cout << "l1-norm error (absolute) = " << fabs(l1x - l1y) << "." << endl;
            cout << "l1-norm error (relative) = " << (fabs(l1x - l1y))/l1x << "." << endl;

            return 0;
        }

   **Last Modified:** November/2018
