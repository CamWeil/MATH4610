16. **Routine Name:**           nmsqgauss

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will perform Guassian elimination on a square matrix and return the result of the operation in the original array.
   
   **Input:** There are inputs needed for the size of the matrix and the elements of the matrix. These inputs are both prompted for at the beginning of the routine.

   **Output:** This routine simply performs Gaussian elimination on a square matrix until it is in row echelon form, which is then given as the output. For example:
   
        Enter matrix size: 3
        Enter matrix element a11: 1
        Enter matrix element a12: 2
        Enter matrix element a13: 3
        Enter matrix element a21: 4
        Enter matrix element a22: 5
        Enter matrix element a23: 6
        Enter matrix element a31: 7
        Enter matrix element a32: 8
        Enter matrix element a33: 9
        A (GE) = 
        ----------
         7  8  9 
         0  0.857143  1.71429 
         0  0  1.11022e-16 
        ----------

   **Usage/Example:** The routine defines two int variables, n and pivrow, and three double variables, pivot, swap, and c, as well as an array with double elements, a. n represents the size of the matrix, pivot is used to locate maximum values for row swapping, and pivrow is used to store the value of the row that each pivot was found in. swap is used to exchange rows when pivots are found, c is used to compute various coefficents from each row that can be used in the elimination process, and a represents the matrix itself. Rows are eliminated using the loop:
   
        for(int i = 0; i < n; i++){
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

   **Implementation/Code:** The following is the code for nmsqgauss.cpp:

        #include<iostream>
        #include<math.h>
        using namespace std;

        int n;

        int main(){
            cout << "Enter matrix size: ";
            cin >> n;

            double a[n][n];
            double pivot;
            int pivrow;
            double swap;
            double c;

            for(int i = 0; i < n; i++){
                for(int j = 0; j < n; j++){
                    cout << "Enter matrix element a" << i + 1 << j + 1 << ": ";
                    cin >> a[i][j];
                }
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

                for(int j = 0; j < n; j++){
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

            cout << "A (GE) = " << endl;
            cout << "----------" << endl;

            for(int i = 0; i < n; i++){
                for(int j = 0; j < n; j++){
                    cout << " " << a[i][j] << " ";

                    if(j == n - 1){
                        cout << endl;
                    }
                }
            }

            cout << "----------" << endl;
            cout << endl;

            return 0;
        }

   **Last Modified:** November/2018
