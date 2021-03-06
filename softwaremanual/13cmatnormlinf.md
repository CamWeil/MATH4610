13c. **Routine Name:**           nmmatnormlinf

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will compute and return the l<sub>∞</sub> norm of a given matrix of arbitrary size.
   
   **Input:** There are inputs needed for the size of the matrix and the elements of the matrix. These inputs are both prompted for at the beginning of the routine.

   **Output:** This routine simply calculates the maximum sum of the magnitude of the rows of the matrix, which is then given as the output. For example:
 
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
        l∞-norm = 24.

   **Usage/Example:** The routine defines one double variable, linfn, as well as two int variables, m and n, an array with double elements, a, and a vector with double elements, linf. m and n represent the rows and columns of the matrix, respectively, linfn represents the l<sub>∞</sub> norm of the matrix, and a represents the matrix itself. The vector linf is used to collect the sum of the magnitude of the values of each matrix row, so that the norm can be calculated using the loops:
   
        for(int j = 0; j < n; j ++){
                for(int i = 0; i < m; i++){
                    linf[i] = linf[i] + fabs(a[i][j]);
                }
            }

            for(vector<double>::size_type k = 0; k < m; k++){
                if(linf[k] > linfn){
                    linfn = linf[k];
                }

                else{
                    linfn = linfn;
                }
            }

   **Implementation/Code:** The following is the code for nmmatnormlinf.cpp:

        #include<iostream>
        #include<math.h>
        #include<vector>
        using namespace std;

        int m, n;
        double linfn = 0;

        int main(){
            cout << "Enter matrix size (number of rows): ";
            cin >> m;

            cout << "Enter matrix size (number of columns): ";
            cin >> n;

            double a[m][n];
            vector<double> linf(m);

            for(int i = 0; i < m; i++){
                for(int j = 0; j < n; j++){
                    cout << "Enter matrix element a" << i + 1 << j + 1 << ": ";
                    cin >> a[i][j];
                }
            }

            for(int j = 0; j < n; j ++){
                for(int i = 0; i < m; i++){
                    linf[i] = linf[i] + fabs(a[i][j]);
                }
            }

            for(vector<double>::size_type k = 0; k < m; k++){
                if(linf[k] > linfn){
                    linfn = linf[k];
                }

                else{
                    linfn = linfn;
                }
            }

            cout << "l∞-norm = " << linfn << "." << endl;

            return 0;
        }

   **Last Modified:** November/2018
