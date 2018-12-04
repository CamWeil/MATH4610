20. **Routine Name:**           nmlinsysgauss

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will perform Gaussian elimination on a square matrix and return the solution x to a problem Ax = b.
   
   **Input:** There are inputs needed for the size of the matrix, the elements of the matrix, and the elements of the vector b. These inputs are all prompted for at the beginning of the routine.

   **Output:** This routine simply performs Gaussian elimination on an augmented square matrix until it is in row echelon form, and then performs backward substitution so as to solve for x given Ax = b, where x is then given as the output. For example:
        
        Enter size of linear system: 3
        Enter coefficient #1 for equation #1: 1
        Enter coefficient #2 for equation #1: 1
        Enter coefficient #3 for equation #1: 1
        Enter coefficient #1 for equation #2: 4
        Enter coefficient #2 for equation #2: 3
        Enter coefficient #3 for equation #2: -1
        Enter coefficient #1 for equation #3: 3
        Enter coefficient #2 for equation #3: 5
        Enter coefficient #3 for equation #3: 3
        Enter constant term #1 for equation #1: 1
        Enter constant term #2 for equation #2: 6
        Enter constant term #3 for equation #3: 4
        A (GE) = 
        ----------
         4  3  -1  |  6 
         0  2.75  3.75  |  -0.5 
         0  0  0.909091  |  -0.454545 
        ----------
        
        x = < 1  0.5  -0.5 >.

   **Usage/Example:** The routine defines two int variables, n and pivrow, and four double variables, pivot, swap, c, and s, as well as an array with double elements, a, and a vector with double elements, x. n represents the size of the matrix, pivot is used to locate maximum values for row swapping, and pivrow is used to store the value of the row that each pivot was found in. swap is used to exchange rows when pivots are found, c is used to compute various coefficents from each row that can be used in the elimination process, s represents the sum in the implementation of the formula for forward substitution, and a and x each represent their respective parts of the system Ax = b. The elements of x are calculated using the loop:
   
        x[n - 1] = a[n - 1][n]/a[n - 1][n - 1];
    
        for(int i = n - 2; -1 < i; i--){
            s = 0;

            for(int j = i + 1; j < n; j++){
                s = s + a[i][j]*x[j];
            }

            x[i] = (a[i][n] - s)/a[i][i];
        }

   **Implementation/Code:** The following is the code for nmlinsysgauss.cpp:

        #include<iostream>
        #include<math.h>
        #include<vector>
        using namespace std;

        int n;

        int main(){
            cout << "Enter size of linear system: ";
            cin >> n;

            double a[n][n + 1];
            vector<double> x(n);

            double pivot = fabs(a[0][0]);
            int pivrow = 0;
            double swap;
            double c;
            double s;

            for(int i = 0; i < n; i++){
                for(int j = 0; j < n; j++){
                    cout << "Enter coefficient #" << j + 1 << " for equation #" << i + 1 << ": ";
                    cin >> a[i][j];
                }
            }

            for(int i = 0; i < n; i++){
                cout << "Enter constant term #" << i + 1 << " for equation #" << i + 1 << ": ";
                cin >> a[i][n];
            }

            for(int i = 0; i < n; i++){
                pivot = fabs(a[i][i]);
                pivrow = i;

                for(int j = i + 1; j < n; j++){
                    if(fabs(a[j][i]) > pivot){
                        pivot = fabs(a[j][i]);
                        pivrow = j;
                    }
                }

                for(int j = 0; j < n + 1; j++){
                    swap = a[pivrow][j];
                    a[pivrow][j] = a[i][j];
                    a[i][j] = swap;
                }

                for (int j = i + 1; j < n; j++){
                    c = -a[j][i]/a[i][i];

                    for(int k = i; k < n + 1; k++){
                        if(i == k){
                            a[j][k] = 0;
                        }

                        else{
                            a[j][k] = a[j][k] + c*a[i][k];
                        }
                    }
                }
            }

            x[n - 1] = a[n - 1][n]/a[n - 1][n - 1];

            for(int i = n - 2; -1 < i; i--){
                s = 0;

                for(int j = i + 1; j < n; j++){
                    s = s + a[i][j]*x[j];
                }

                x[i] = (a[i][n] - s)/a[i][i];
            }

            cout << "A (GE) = " << endl;
            cout << "----------" << endl;

            for(int i = 0; i < n; i++){
                for(int j = 0; j < n + 1; j++){
                    cout << " " << a[i][j] << " ";

                    if(j == n - 1){
                        cout << " | ";
                    }

                    if(j == n){
                        cout << endl;
                    }
                }
            }

            cout << "----------" << endl;
            cout << endl;

            cout << "x = <";

            for(int i = 0; i < n; i++){
                cout << " " << x[i] << " ";
            }

            cout << ">." << endl;

            return 0;
        }

   **Last Modified:** December/2018
