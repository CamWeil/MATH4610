24. **Routine Name:**           nmlinsyschol

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will perform Cholesky factorization on a symmetric matrix and return the solution x to a problem Ax = b.
   
   **Input:** There are inputs needed for the size of the matrix, the elements of the matrix, and the elements of the vector b. These inputs are all prompted for at the beginning of the routine.

   **Output:** This routine simply performs Cholesky factorization on a symmetric matrix, and then performs respective substitutions so as to solve for y given Ly = b and x given L<sup>T</sup>x = y, where x is then given as the output. For example:
        
        Enter size of linear system: 5
        Enter coefficient #1 for equation #1: 1
        Enter coefficient #2 for equation #1: 1
        Enter coefficient #3 for equation #1: 1
        Enter coefficient #4 for equation #1: 1
        Enter coefficient #5 for equation #1: 1
        Enter coefficient #1 for equation #2: 1
        Enter coefficient #2 for equation #2: 2
        Enter coefficient #3 for equation #2: 3
        Enter coefficient #4 for equation #2: 4
        Enter coefficient #5 for equation #2: 5
        Enter coefficient #1 for equation #3: 1
        Enter coefficient #2 for equation #3: 3
        Enter coefficient #3 for equation #3: 6
        Enter coefficient #4 for equation #3: 10
        Enter coefficient #5 for equation #3: 15
        Enter coefficient #1 for equation #4: 1
        Enter coefficient #2 for equation #4: 4
        Enter coefficient #3 for equation #4: 10
        Enter coefficient #4 for equation #4: 20
        Enter coefficient #5 for equation #4: 35
        Enter coefficient #1 for equation #5: 1
        Enter coefficient #2 for equation #5: 5
        Enter coefficient #3 for equation #5: 15
        Enter coefficient #4 for equation #5: 35
        Enter coefficient #5 for equation #5: 70
        Enter constant term #1 for equation #1: 5
        Enter constant term #2 for equation #2: 4
        Enter constant term #3 for equation #3: 3
        Enter constant term #4 for equation #4: 2
        Enter constant term #5 for equation #5: 1
        L = 
        ----------
         1  0  0  0  6.95313e-310 
         1  1  0  0  9.65595e-97 
         1  2  1  6.95323e-310  1.4822e-323 
         1  3  3  1  1.43279e-322 
         1  4  6  4  1 
        ----------

        L^T = 
        ----------
         1  1  1  1  1 
         0  1  2  3  4 
         0  0  1  3  6 
         0  0  6.95323e-310  1  4 
         6.95313e-310  9.65595e-97  1.4822e-323  1.43279e-322  1 
        ----------

        b = < 5  4  3  2  1 >.
        y = < 5  -1  0  0  0 >.
        x = < 6  -1  0  0  0 >.

   **Usage/Example:** The routine defines one int variable, n, and three double variables, s, s1, and s2, as well as three arrays with double elements, a, l, and lt, and three vectors with double elements, b, x, and y. n represents the size of the matrix, s represents the sum in the implementation of the formula for Cholesky factorization, and s1 and s2 represent the sums in the implementation of the formulas for forward and backward substitution. l represents the lower triangular decomposition of a, lt represents the transpose of the lower triangular decomposition of a, and a, x, y, and b each represent their respective parts of the systems Ly = b and L<sup>T</sup>x = y. The elements of y and x are calculated using the loops:
   
        y[0] = b[0]/l[0][0];

        for(int i = 1; i < n; i++){
            s1 = 0;

            for(int j = 0; j < i; j++){
                s1 = s1 + l[i][j]*y[j];
            }

            y[i] = (b[i] - s1)/l[i][i];
        }

        x[n - 1] = y[n - 1]/lt[n - 1][n - 1];

        for(int i = n - 2; -1 < i; i--){
            s2 = 0;

            for(int j = i + 1; j < n; j++){
                s2 = s2 + lt[i][j]*x[j];
            }

            x[i] = (y[i] - s2)/lt[i][i];
        }

   **Implementation/Code:** The following is the code for nmlinsyschol.cpp:

        #include<iostream>
        #include<math.h>
        #include<vector>
        using namespace std;

        int n;

        int main(){
            cout << "Enter size of linear system: ";
            cin >> n;

            double a[n][n];
            double l[n][n];
            double lt[n][n];
            vector<double> b(n);
            vector<double> x(n);
            vector<double> y(n);
            double s;
            double s1;
            double s2;


            for(int i = 0; i < n; i++){
                for(int j = 0; j < n; j++){
                    cout << "Enter coefficient #" << j + 1 << " for equation #" << i + 1 << ": ";
                    cin >> a[i][j];
                }
            }

            for(vector<double>::size_type i = 0; i < n; i++){
                cout << "Enter constant term #" << i + 1 << " for equation #" << i + 1 << ": ";
                cin >> b[i];
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

            for(int i = 0; i < n; i++){
                for(int j = 0; j < n; j++){
                    lt[i][j] = l[j][i];
                }
            }

            y[0] = b[0]/l[0][0];

            for(int i = 1; i < n; i++){
                s1 = 0;

                for(int j = 0; j < i; j++){
                    s1 = s1 + l[i][j]*y[j];
                }

                y[i] = (b[i] - s1)/l[i][i];
            }

            x[n - 1] = y[n - 1]/lt[n - 1][n - 1];

            for(int i = n - 2; -1 < i; i--){
                s2 = 0;

                for(int j = i + 1; j < n; j++){
                    s2 = s2 + lt[i][j]*x[j];
                }

                x[i] = (y[i] - s2)/lt[i][i];
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
                    cout << " " << lt[i][j] << " ";

                    if(j == n - 1){
                        cout << endl;
                    }
                }
            }

            cout << "----------" << endl;
            cout << endl;

            cout << "b = <";

            for(int i = 0; i < n; i++){
                cout << " " << b[i] << " ";
            }

            cout << ">." << endl;

            cout << "y = <";

            for(int i = 0; i < n; i++){
                cout << " " << y[i] << " ";
            }

            cout << ">." << endl;

            cout << "x = <";

            for(int i = 0; i < n; i++){
                cout << " " << x[i] << " ";
            }

            cout << ">." << endl;

            return 0;
        }

   **Last Modified:** December/2018
