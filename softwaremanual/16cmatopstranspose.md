16c. **Routine Name:**           nmmatopstranspose

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will compute and return the transpose of a matrix (A<sup>T</sup>).
   
   **Input:** There are inputs needed for the size of the matrix and the elements of the matrix. These inputs are both prompted for at the beginning of the routine.

   **Output:** This routine simply calculates the transpose of a matrix by swapping the elements of its rows and columns, which is then given as the output. For example:
   
        Enter matrix size (number of rows): 2
        Enter matrix size (number of columns): 2
        Enter matrix element a11: 1
        Enter matrix element a12: 2
        Enter matrix element a21: 3
        Enter matrix element a22: 4
        A^T = 
        ----------
         1  3 
         2  4 
        ----------

   **Usage/Example:** The routine defines two int variables, m and n, as well as two matrices with double elements, a and cc. m and n represent the rows and columns of the matrix, respectively, cc represents the transpose of the matrix, and a represents the matrix itself. The value of cc is calculated using the loop:
   
        for(int i = 0; i < m; i++){
                for(int j = 0; j < n; j++){
                    cc[i][j] = a[j][i];
            }
        }

   **Implementation/Code:** The following is the code for nmmatopstranspose.cpp:

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
            double cc[m][n];

            for(int i = 0; i < m; i++){
                for(int j = 0; j < n; j++){
                    cout << "Enter matrix element a" << i + 1 << j + 1 << ": ";
                    cin >> a[i][j];
                }
            }

            cout << "A^T = " << endl;
            cout << "----------" << endl;

            for(int i = 0; i < m; i++){
                for(int j = 0; j < n; j++){
                    cc[i][j] = a[j][i];
                    cout << " " << cc[i][j] << " ";

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
