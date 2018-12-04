22. **Routine Name:**           nmlinsyslu

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will perform LU-factorization on a square matrix and return the solution x to a problem Ax = b.
   
   **Input:** There are inputs needed for the size of the matrix, the elements of the matrix, and the elements of the vector b. These inputs are all prompted for at the beginning of the routine.

   **Output:** This routine simply performs LU-factorization on a square matrix, and then performs respective substitutions so as to solve for y given Ly = b and x given Ux = b, where x is then given as the output. For example:
        
        Enter size of linear system: 3
        Enter coefficient #1 for equation #1: 1
        Enter coefficient #2 for equation #1: 1
        Enter coefficient #3 for equation #1: 1
        Enter coefficient #1 for equation #2: 4
        Enter coefficient #2 for equation #2: 3
        Enter coefficient #3 for equation #2: -1
        Enter coefficient #1 for equation #3: 3
        Enter coefficient #2 for equation #3: 5
        Enter coefficient #3 for equation #3: 3
        Enter constant term #1 for equation #1: 1
        Enter constant term #2 for equation #2: 6
        Enter constant term #3 for equation #3: 4
        L = 
        ----------
         1  0  0 
         0.75  1  0 
         0.25  0.0909091  1 
        ----------

        U = 
        ----------
         4  3  -1 
         0  2.75  3.75 
         0  0  0.909091 
        ----------

        b = < 6  4  1 >.
        y = < 6  -0.5  -0.454545 >.
        x = < 1  0.5  -0.5 >.

   **Usage/Example:** The routine defines two int variables, n and pivrow, and five double variables, pivot, swap, c, s1, and s2, as well as three arrays with double elements, a, u, and l, and two vectors with double elements, b and x. n represents the size of the matrix, pivot is used to locate maximum values for row swapping, and pivrow is used to store the value of the row that each pivot was found in. swap is used to exchange rows when pivots are found, c is used to compute various coefficents from each row that can be used in the elimination process, s1 and s2 represent the sums in the implementation of the formulas for forward and backward substitution. u represents the upper triangular decomposition of a, l represents the lower triangular decomposition of a, and a, x, and b each represent their respective parts of the system Ax = b. The elements of y and x are calculated using the loops:
   
        y[0] = b[0]/l[0][0];

        for(int i = 1; i < n; i++){
            s1 = 0;

            for(int j = 0; j < i; j++){
                s1 = s1 + l[i][j]*y[j];
            }

            y[i] = (b[i] - s1)/l[i][i];
        }

        x[n - 1] = y[n - 1]/u[n - 1][n - 1];

        for(int i = n - 2; -1 < i; i--){
            s2 = 0;

            for(int j = i + 1; j < n; j++){
                s2 = s2 + u[i][j]*x[j];
            }

            x[i] = (y[i] - s2)/u[i][i];
        }

   **Implementation/Code:** The following is the code for nmlinsyslu.cpp:

        #include<iostream>
        #include<math.h>
        #include<vector>
        using namespace std;

        int n;

        int main(){
            cout << "Enter size of linear system: ";
            cin >> n;

            double a[n][n];
            double u[n][n];
            double l[n][n];
            vector<double> b(n);
            vector<double> x(n);
            vector<double> y(n);

            double pivot = fabs(a[0][0]);
            int pivrow = 0;
            double swap;
            double c;
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

                    swap = b[pivrow];
                    b[pivrow] = b[i];
                    b[i] = swap;
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

            y[0] = b[0]/l[0][0];

            for(int i = 1; i < n; i++){
                s1 = 0;

                for(int j = 0; j < i; j++){
                    s1 = s1 + l[i][j]*y[j];
                }

                y[i] = (b[i] - s1)/l[i][i];
            }

            x[n - 1] = y[n - 1]/u[n - 1][n - 1];

            for(int i = n - 2; -1 < i; i--){
                s2 = 0;

                for(int j = i + 1; j < n; j++){
                    s2 = s2 + u[i][j]*x[j];
                }

                x[i] = (y[i] - s2)/u[i][i];
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
