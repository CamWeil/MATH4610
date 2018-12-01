16g. **Routine Name:**           nmmatopsmultmat

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will compute and return the product of two square matrices (A * B).
   
   **Input:** There are inputs needed for the size of the matrices and the elements of the matrices. These inputs are both prompted for at the beginning of the routine.

   **Output:** This routine simply calculates the product of two matrices by the rules of matrix multiplication, which is then given as the output. For example:
   
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
        A * B = 
        ----------
         19  22 
         43  50 
        ----------

   **Usage/Example:** The routine defines two int variables, m and n, as well as three matrices with double elements, a, b, and cg. m and n represent the rows and columns of the matrix, respectively, cg represents the product of the two matrices, and a and b represent the matrices themselves. The value of cg is calculated using the loop:
   
        for(int i = 0; i < n; i++){
            for(int j = 0; j < n; j++){
                for(int k = 0; k < n; k++){
                    cg[i][j] = cg[i][j] + a[i][k]*b[k][j];
                }
            }
        }

   **Implementation/Code:** The following is the code for nmmatopsmultmat.cpp:

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
            double cg[n][n];

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

            if(m == n){
                cout << "A * B = " << endl;
                cout << "----------" << endl;

                for(int i = 0; i < n; i++){
                    for(int j = 0; j < n; j++){
                        for(int k = 0; k < n; k++){
                            cg[i][j] = cg[i][j] + a[i][k]*b[k][j];
                        }
                        cout << " " << cg[i][j] << " ";

                        if(j == n - 1){
                            cout << endl;
                        }
                    }
                }
            }

            cout << "----------" << endl;
            cout << endl;

            return 0;
        }

   **Last Modified:** November/2018