14h. **Routine Name:**           nmmatopskron

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will compute and return the Kronecker product of two matrices (A ⊗ B).
   
   **Input:** There are inputs needed for the size of the matrices and the elements of the matrices. These inputs are both prompted for at the beginning of the routine.

   **Output:** This routine simply calculates the Kronecker product of two matrices by multiplying each element of the first matrix by each element of the second matrix, which is then given as the output. For example:
   
        Enter matrix size (number of rows): 2
        Enter matrix size (number of columns): 2
        Enter matrix element a11: 1
        Enter matrix element a12: 2
        Enter matrix element a21: 3
        Enter matrix element a22: 4
        Enter matrix element b11: 5
        Enter matrix element b12: 6
        Enter matrix element b21: 7
        Enter matrix element b22: 8
        A ⊗ B = 
        ----------
         5  6  10  12 
         7  8  14  16 
         15  18  20  24 
         21  24  28  32 
        ----------

   **Usage/Example:** The routine defines two int variables, m and n, as well as three arrays with double elements, a, b, and ch. m and n represent the rows and columns of the matrix, respectively, ch represents the Kronecker product of the two matrices, and a and b represent the matrices themselves. The value of ch is calculated using the loop:
   
        for(int i = 0; i < m; i++){
            for(int k = 0; k < m; k++){
                for(int j = 0; j < n; j++){
                    for(int l = 0; l < n; l++){
                        ch[i + l + 1][j + k + 1] = a[i][j]*b[k][l];
                    }
                }
            }
        }

   **Implementation/Code:** The following is the code for nmmatopskron.cpp:

        #include<iostream>
        #include<math.h>
        #include<vector>
        using namespace std;

        int m, n;

        int main(){

            cout << "Enter matrix size (number of rows): ";
            cin >> m;

            cout << "Enter matrix size (number of columns): ";
            cin >> n;

            double a[m][n];
            double b[m][n];
            double ch[m*m][n*n];

            for(int i = 0; i < m; i++){
                for(int j = 0; j < n; j++){
                    cout << "Enter matrix element a" << i + 1 << j + 1 << ": ";
                    cin >> a[i][j];
                }
            }
            
            for(int i = 0; i < m; i++){
                for(int j = 0; j < n; j++){
                    cout << "Enter matrix element b" << i + 1 << j + 1 << ": ";
                    cin >> b[i][j];
                }
            }

            cout << "A ⊗ B = " << endl;
            cout << "----------" << endl;

            for(int i = 0; i < m; i++){
                for(int k = 0; k < m; k++){
                    for(int j = 0; j < n; j++){
                        for(int l = 0; l < n; l++){
                            ch[i + l + 1][j + k + 1] = a[i][j]*b[k][l];
                            cout << " " << ch[i + l + 1][j + k + 1] << " ";

                            if(l == n - 1 && j == n - 1){
                                cout << endl;
                            }
                        }
                    }
                }
            }

            cout << "----------" << endl;
            cout << endl;

            return 0;
        }

   **Last Modified:** November/2018
