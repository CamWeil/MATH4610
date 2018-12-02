14e. **Routine Name:**           nmmatopsmultsc

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will compute and return the product of a scalar and a matrix (c * A).
   
   **Input:** There are inputs needed for the size of the matrix, the elements of the matrix, and the value of the scalar. These inputs are all prompted for at the beginning of the routine.

   **Output:** This routine simply calculates the product of a scalar and a matrix by multiplying each respective element of the matrix by the scalar, which is then given as the output. For example:
   
        Enter matrix size (number of rows): 2
        Enter matrix size (number of columns): 2
        Enter scalar c: 2
        Enter matrix element a11: 1
        Enter matrix element a12: 2
        Enter matrix element a21: 3
        Enter matrix element a22: 4
        c * A = 
        ----------
         2  4 
         6  8 
        ----------

   **Usage/Example:** The routine defines two int variables, m and n, and a double variable, c, as well as two arrays with double elements, a and ce. m and n represent the rows and columns of the matrix, respectively, c represents the scalar, ce represents the product of the scalar and the matrix, and a represents the matrix itself. The value of ce is calculated using the loop:
   
        for(int i = 0; i < m; i++){
            for(int j = 0; j < n; j++){
                ce[i][j] = c*a[i][j];
            }
        }

   **Implementation/Code:** The following is the code for nmmatopsmultsc.cpp:

        #include<iostream>
        #include<math.h>
        #include<vector>
        using namespace std;

        int m, n;
        double c;

        int main(){

            cout << "Enter matrix size (number of rows): ";
            cin >> m;

            cout << "Enter matrix size (number of columns): ";
            cin >> n;
            
            cout << "Enter scalar c: ";
            cin >> c;

            double a[m][n];
            double ce[m][n];

            for(int i = 0; i < m; i++){
                for(int j = 0; j < n; j++){
                    cout << "Enter matrix element a" << i + 1 << j + 1 << ": ";
                    cin >> a[i][j];
                }
            }

            cout << "c * A = " << endl;
            cout << "----------" << endl;

            for(int i = 0; i < m; i++){
                for(int j = 0; j < n; j++){
                    ce[i][j] = c*a[i][j];
                    cout << " " << ce[i][j] << " ";

                    if(j == n - 1){
                        cout << endl;
                    }
                }
            }

            return 0;
        }

   **Last Modified:** November/2018
