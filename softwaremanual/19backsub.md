19. **Routine Name:**           nmbacksub

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will perform backward substitution on a square upper triangular matrix and return the solution x to a problem Ax = b.
   
   **Input:** There are inputs needed for the size of the matrix, the elements of the matrix, and the elements of the vector b. These inputs are all prompted for at the beginning of the routine.

   **Output:** This routine simply performs forward substitution on a square upper triangular matrix so as to solve for x given Ax = b, where x is then given as the output. For example:
        
        Enter matrix size: 3
        Enter matrix element a11: 1
        Enter matrix element a12: 2
        Enter matrix element a13: 3
        Enter matrix element a21: 0
        Enter matrix element a22: 4
        Enter matrix element a23: 5
        Enter matrix element a31: 0
        Enter matrix element a32: 0
        Enter matrix element a33: 6
        Enter coordinate #1 for vector b: 1
        Enter coordinate #2 for vector b: 2
        Enter coordinate #3 for vector b: 3
        x = < -0.25  -0.125  0.5 >.

   **Usage/Example:** The routine defines one int variable, n, and one double variable, s, as well as an array with double elements, a, and two vectors with double elements, b and x. n represents the size of the matrix, s represents the sum in the implementation of the formula for backward substitution, and a, x, and b each represent their respective parts of the system Ax = b. The elements of x are calculated using the loop:
   
        x[n - 1] = b[n - 1]/a[n - 1][n - 1];

        for(int i = n - 2; -1 < i; i--){
            s = 0;

            for(int j = i + 1; j < n; j++){
                s = s + a[i][j]*x[j];
            }

            x[i] = (b[i] - s)/a[i][i];
        }

   **Implementation/Code:** The following is the code for nmbacksub.cpp:

        #include<iostream>
        #include<math.h>
        #include<vector>
        using namespace std;

        int n;

        int main(){
            cout << "Enter matrix size: ";
            cin >> n;

            double a[n][n];
            vector<double> b(n);
            vector<double> x(n);
            double s;

            for(int i = 0; i < n; i++){
                for(int j = 0; j < n; j++){
                    cout << "Enter matrix element a" << i + 1 << j + 1 << ": ";
                    cin >> a[i][j];
                }
            }

            for(vector<double>::size_type i = 0; i < n; i++){
                cout << "Enter coordinate #" << i + 1 << " for vector b: ";
                cin >> b[i];
            }

            for(int j = 0; j < n; j++){
                for(int i = j + 1; i < n; i++){
                    if(a[i][j] != 0){
                        cout << "Error: This routine is for upper triangular matrices." << endl;
                        return 0;
                    }

                    else if(a[j][j] == 0){
                        cout << "Error: This routine is for matrices with nonzero diagonal elements." << endl;
                        return 0;
                    }
                }
            }

            x[n - 1] = b[n - 1]/a[n - 1][n - 1];

            for(int i = n - 2; -1 < i; i--){
                s = 0;

                for(int j = i + 1; j < n; j++){
                    s = s + a[i][j]*x[j];
                }

                x[i] = (b[i] - s)/a[i][i];
            }

            cout << "x = <";

            for(int i = 0; i < n; i++){
                cout << " " << x[i] << " ";
            }

            cout << ">." << endl;

            return 0;
        }

   **Last Modified:** December/2018
