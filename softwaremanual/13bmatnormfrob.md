13b. **Routine Name:**           nmmatnormfrob

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will compute and return the Frobenius norm of a given matrix of arbitrary size.
   
   **Input:** There are inputs needed for the size of the matrix and the elements of the matrix. These inputs are both prompted for at the beginning of the routine.

   **Output:** This routine simply calculates the square root of the sum of the of the squares of each element of the matrix, which is then given as the output. For example:
 
        Enter matrix size (number of rows): 3
        Enter matrix size (number of columns): 3
        Enter matrix element a11: 1
        Enter matrix element a12: 2
        Enter matrix element a13: 3
        Enter matrix element a21: 4
        Enter matrix element a22: 5
        Enter matrix element a23: 6
        Enter matrix element a31: 7
        Enter matrix element a32: 8
        Enter matrix element a33: 9
        Frobenius norm = 16.8819.

   **Usage/Example:** The routine defines one double variable, frobn, as well as two int variables, m and n, and an array with double elements, a. m and n represent the rows and columns of the matrix, respectively, frobn represents the Frobenius norm of the matrix, and a represents the matrix itself. The Frobenius norm is calculated using the loop:
   
        for(int i = 0; i < m; i ++){
            for(int j = 0; j < n; j++){
                frobn = frobn + fabs(a[i][j])*fabs(a[i][j]);
            }
        }

        frobn = sqrt(frobn);

   **Implementation/Code:** The following is the code for nmmatnormfrob.cpp:

        #include<iostream>
        #include<math.h>
        #include<vector>
        using namespace std;

        int m, n;
        double frobn = 0;

        int main(){
            cout << "Enter matrix size (number of rows): ";
            cin >> m;

            cout << "Enter matrix size (number of columns): ";
            cin >> n;

            double a[m][n];

            for(int i = 0; i < m; i++){
                for(int j = 0; j < n; j++){
                    cout << "Enter matrix element a" << i + 1 << j + 1 << ": ";
                    cin >> a[i][j];
                }
            }

            for(int i = 0; i < m; i ++){
                for(int j = 0; j < n; j++){
                    frobn = frobn + fabs(a[i][j])*fabs(a[i][j]);
                }
            }

            frobn = sqrt(frobn);

            cout << "Frobenius norm = " << frobn << "." << endl;

            return 0;
        }

   **Last Modified:** November/2018
