17. **Routine Name:**           nmrectgauss

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will perform Guassian elimination on a rectangular matrix and return the result of the operation in the original array.
   
   **Input:** There are inputs needed for the size of the matrix and the elements of the matrix. These inputs are both prompted for at the beginning of the routine.

   **Output:** This routine simply performs Gaussian elimination on a rectangular matrix until it is in row echelon form, which is then given as the output. For example:
        
        Enter matrix size (number of rows): 2
        Enter matrix size (number of columns): 3
        Enter matrix element a11: 1
        Enter matrix element a12: 2
        Enter matrix element a13: 3
        Enter matrix element a21: 4
        Enter matrix element a22: 5
        Enter matrix element a23: 6
        A (GE) = 
        ----------
         1  1.25  1.5 
         0  1  2 
        ----------

   **Usage/Example:** The routine defines three int variables, m, n, and pivrow, and four double variables, pivot, swap, c1, and c2, as well as an array with double elements, a. m and n represent the rows and columns of the matrix, respectively, pivot is used to locate the largest value in the first column of the matrix, and pivrow is used to store the value of the row that the pivot was found in. swap is used to move the row that the pivot was found in to the first row, and vice versa, c1 is used to compute various coefficents from the first row that can be used in the elimination process, c2 is used to reduce each pivot back to 1 after the elimination process is complete, and a represents the matrix itself. Once swapping occurs, rows are eliminated using the loop:
   
        for(int i = 0; i < m; i++){
            for (int j = i + 1; j < m; j++){
                c1 = -a[j][i]/a[i][i];

                for(int k = i; k < m + 1; k++){
                    if(i == k){
                        a[j][k] = 0;
                    }

                    else{
                        a[j][k] = a[j][k] + c1*a[i][k];
                    }
                }
            }
        }

   **Implementation/Code:** The following is the code for nmrectgauss.cpp:

        #include<iostream>
        #include<math.h>
        using namespace std;

        int m, n;

        int main(){
            cout << "Enter matrix size (number of rows): ";
            cin >> m;

            cout << "Enter matrix size (number of columns): ";
            cin >> n;

            if(m == n){
                cout << "Error: This is a routine for rectangular matrices." << endl;
                return 0;
            }

            double a[m][n];
            double pivot = fabs(a[0][0]);
            int pivrow = 0;
            double swap;
            double c1;
            double c2;

            for(int i = 0; i < m; i++){
                for(int j = 0; j < n; j++){
                    cout << "Enter matrix element a" << i + 1 << j + 1 << ": ";
                    cin >> a[i][j];
                }
            }

            for(int i = 0; i < m; i++){
                if(fabs(a[i][0]) > pivot){
                    pivot = fabs(a[i][0]);
                    pivrow = i;
                }

                else{
                    pivot = pivot;
                    pivrow = pivrow;
                }
            }

            for(int j = 0; j < n; j++){
                swap = a[pivrow][j];
                a[pivrow][j] = a[0][j];
                a[0][j] = swap;
            }

            for(int i = 0; i < m; i++){
                for (int j = i + 1; j < m; j++){
                    c1 = -a[j][i]/a[i][i];

                    for(int k = i; k < m + 1; k++){
                        if(i == k){
                            a[j][k] = 0;
                        }

                        else{
                            a[j][k] = a[j][k] + c1*a[i][k];
                        }
                    }
                }
            }

            if(m < n){
                for(int i = 0; i < n; i++){
                    c2 = a[i][i];

                    for(int j = 0; j < n; j++){
                        if(a[i][j] == 0){
                            a[i][j] = 0;
                        }

                        else{
                            a[i][j] = a[i][j]/c2;
                        }
                    }
                }
            }

            else if(m > n){
                for(int i = 0; i < m; i++){
                    c2 = a[i][i];

                    for(int j = 0; j < m; j++){
                        if(a[i][j] == 0){
                            a[i][j] = 0;
                        }

                        else{
                            a[i][j] = a[i][j]/c2;
                        }
                    }
                }
            }

            else{
                cout << "Error: This is a routine for rectangular matrices." << endl;
                return 0;
            }

            cout << "A (GE) = " << endl;
            cout << "----------" << endl;

            for(int i = 0; i < m; i++){
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
