23. **Routine Name:**           nmcholfact

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will perform Cholesky factorization on a symmetric matrix and return the results of the operations in two separate arrays.
   
   **Input:** There are inputs needed for the size of the matrix and the elements of the matrix. These inputs are both prompted for at the beginning of the routine.

   **Output:** This routine simply performs Cholesky factorization on a symmetric matrix to create a resultant lower triangular matrix and its transpose, which are then given as the output. For example:
        
        Enter matrix size: 5
        Enter matrix element a11: 1
        Enter matrix element a12: 1
        Enter matrix element a13: 1
        Enter matrix element a14: 1
        Enter matrix element a15: 1
        Enter matrix element a21: 1
        Enter matrix element a22: 2
        Enter matrix element a23: 3
        Enter matrix element a24: 4
        Enter matrix element a25: 5
        Enter matrix element a31: 1
        Enter matrix element a32: 3
        Enter matrix element a33: 6
        Enter matrix element a34: 10
        Enter matrix element a35: 15
        Enter matrix element a41: 1
        Enter matrix element a42: 4
        Enter matrix element a43: 10
        Enter matrix element a44: 20
        Enter matrix element a45: 35
        Enter matrix element a51: 1
        Enter matrix element a52: 5
        Enter matrix element a53: 15
        Enter matrix element a54: 35
        Enter matrix element a55: 70
        L = 
        ----------
         1  0  0  0  6.95313e-310 
         1  1  0  0  9.65595e-97 
         1  2  1  6.95323e-310  1.4822e-323 
         1  3  3  1  9.38725e-323 
         1  4  6  4  1 
        ----------

        L^T = 
        ----------
         1  1  1  1  1 
         0  1  2  3  4 
         0  0  1  3  6 
         0  0  6.95323e-310  1  4 
         6.95313e-310  9.65595e-97  1.4822e-323  9.38725e-323  1 
        ----------

   **Usage/Example:** The routine defines one int variables, n, and one double variable, s, as well as two arrays with double elements, a and l. n represents the size of the matrix, s represents the sum in the implementation of the formula for Cholesky factorization, l represents the lower triangular decomposition of a, and a represents the matrix itself. The elements of l are calculated using the loop:
   
        for(int i = 0; i < n; i++) {
            for(int j = 0; j < i + 1; j++) {
                s = 0;

                if(i == j){
                    for(int k = 0; k < j; k++)
                        s = s + l[j][k]*l[j][k];
                        l[j][j] = sqrt(a[j][j] - s);
                }

                else{
                    for(int k = 0; k < j; k++)
                        s = s + l[i][k]*l[j][k];
                        l[i][j] = (a[i][j] - s)/l[j][j];
                }
            }
        }

   **Implementation/Code:** The following is the code for nmcholfact.cpp:

        #include<iostream>
        #include<math.h>
        using namespace std;

        int n;

        int main(){
            cout << "Enter matrix size: ";
            cin >> n;

            double a[n][n];
            double l[n][n];
            double s;


            for(int i = 0; i < n; i++){
                for(int j = 0; j < n; j++){
                    cout << "Enter matrix element a" << i + 1 << j + 1 << ": ";
                    cin >> a[i][j];
                }
            }

            for(int i = 0; i < n; i++){
                for(int j = 0; j < n; j++){
                    if(a[i][j] != a[j][i]){
                        cout << "Error: This is a routine for symmetric matrices." << endl;
                        return 0;
                    }
                }
            }

            for(int i = 0; i < n; i++) {
                for(int j = 0; j < i + 1; j++) {
                    s = 0;

                    if(i == j){
                        for(int k = 0; k < j; k++)
                            s = s + l[j][k]*l[j][k];
                            l[j][j] = sqrt(a[j][j] - s);
                    }

                    else{
                        for(int k = 0; k < j; k++)
                            s = s + l[i][k]*l[j][k];
                            l[i][j] = (a[i][j] - s)/l[j][j];
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

            cout << "L^T = " << endl;
            cout << "----------" << endl;

            for(int i = 0; i < n; i++){
                for(int j = 0; j < n; j++){
                    cout << " " << l[j][i] << " ";

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
