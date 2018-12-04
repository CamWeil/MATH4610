21. **Routine Name:**           nmlufact

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will perform LU-factorization on a square matrix and return the results of the operations in two separate arrays.
   
   **Input:** There are inputs needed for the size of the matrix and the elements of the matrix. These inputs are both prompted for at the beginning of the routine.

   **Output:** This routine simply performs LU-factorization on a square matrix to create two resultant triangular matrices, which are then given as the output. For example:
        
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
        L = 
        ----------
         1  0  0 
         0.142857  1  0 
         0.571429  0.5  1 
        ----------

        U = 
        ----------
         7  8  9 
         0  0.857143  1.71429 
         0  0  1.11022e-16 
        ----------

   **Usage/Example:** The routine defines two int variables, n and pivrow, and three double variables, pivot, swap, and c, as well as three array with double elements, a, u, and l. n represents the size of the matrix, pivot is used to locate maximum values for row swapping, and pivrow is used to store the value of the row that each pivot was found in. swap is used to exchange rows when pivots are found, c is used to compute various coefficents from each row that can be used in the elimination process, u represents the upper triangular decomposition of a, l represents the lower triangular decomposition of a, and a represents the matrix itself. The elements of u and l are calculated using the loops:
   
        for (int j = i + 1; j < n; j++){
            c = -u[j][i]/u[i][i];
            l[j][i] = -c;
            
            for(int k = i; k < n; k++){
                if(i == k){
                    u[j][k] = 0;
                }
                
                else{
                    u[j][k] = u[j][k] + c*u[i][k];
                }
            }
        }

   **Implementation/Code:** The following is the code for nmlufact.cpp:

        #include<iostream>
        #include<math.h>
        using namespace std;

        int n;

        int main(){
            cout << "Enter matrix size: ";
            cin >> n;

            double a[n][n];
            double l[n][n];
            double u[n][n];
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
                for(int j = 0; j < n; j++){
                    u[i][j] = a[i][j];

                    l[i][j] = 0;
                }
            }

            for(int i = 0; i < n; i++){
                pivot = fabs(u[i][i]);
                pivrow = i;

                for(int j = i + 1; j < n; j++){
                    if(fabs(u[j][i]) > pivot){
                        pivot = fabs(u[j][i]);
                        pivrow = j;
                    }
                }

                for(int j = 0; j < n; j++){
                    swap = u[pivrow][j];
                    u[pivrow][j] = u[i][j];
                    u[i][j] = swap;

                    swap = l[pivrow][j];
                    l[pivrow][j] = l[i][j];
                    l[i][j] = swap;
                }

                for (int j = i + 1; j < n; j++){
                    c = -u[j][i]/u[i][i];
                    l[j][i] = -c;

                    for(int k = i; k < n; k++){
                        if(i == k){
                            u[j][k] = 0;
                        }

                        else{
                            u[j][k] = u[j][k] + c*u[i][k];
                        }
                    }
                }
            }

            for(int i = 0; i < n; i++){
                for(int j = 0; j < n; j++){
                    if(i == j){
                        l[i][j] = 1;
                    }
                }
            }

            cout << "L = " << endl;
            cout << "----------" << endl;

            for(int i = 0; i < n; i++){
                for(int j = 0; j < n; j++){
                    cout << " " << l[i][j] << " ";

                    if(j == n - 1){
                        cout << endl;
                    }
                }
            }

            cout << "----------" << endl;
            cout << endl;

            cout << "U = " << endl;
            cout << "----------" << endl;

            for(int i = 0; i < n; i++){
                for(int j = 0; j < n; j++){
                    cout << " " << u[i][j] << " ";

                    if(j == n - 1){
                        cout << endl;
                    }
                }
            }

            cout << "----------" << endl;
            cout << endl;

            return 0;
        }

   **Last Modified:** December/2018
