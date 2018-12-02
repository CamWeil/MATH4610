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
         4  5  6 
         0  0.75  1.5 
        ----------

   **Usage/Example:** The routine defines three int variables, m, n, and pivrow, and three double variables, pivot, swap, and c, as well as an array with double elements, a. m and n represent the rows and columns of the matrix, respectively, pivot is used to locate maximum values for row swapping, and pivrow is used to store the value of the row that each pivot was found in. swap is used to exchange rows when pivots are found, c is used to compute various coefficents from each row that can be used in the elimination process, and a represents the matrix itself. Rows are eliminated using the loop:
   
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
            double c;

            for(int i = 0; i < m; i++){
                for(int j = 0; j < n; j++){
                    cout << "Enter matrix element a" << i + 1 << j + 1 << ": ";
                    cin >> a[i][j];
                }
            }

            for(int i = 0; i < m; i++){
                pivot = fabs(a[i][i]);
                pivrow = i;

                for(int j = i + 1; j < m; j++){
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

                for (int j = i + 1; j < m; j++){
                    c = -a[j][i]/a[i][i];

                    for(int k = i; k < m + 1; k++){
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
