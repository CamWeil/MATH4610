16d. **Routine Name:**           nmmatopstrace

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will compute and return the trace of a matrix (Tr(A)).
   
   **Input:** There are inputs needed for the size of the matrix and the elements of the matrix. These inputs are both prompted for at the beginning of the routine.

   **Output:** This routine simply calculates the trace of a matrix by adding its diagonal elements together, which is then given as the output. For example:
   
        Enter matrix size (number of rows): 2
        Enter matrix size (number of columns): 2
        Enter matrix element a11: 1
        Enter matrix element a12: 2
        Enter matrix element a21: 3
        Enter matrix element a22: 4
        Tr(A) = 5

   **Usage/Example:** The routine defines two int variables, m and n, and a double variable, cd, as well as a matrices with double elements, a. m and n represent the rows and columns of the matrix, respectively, cd represents the trace of the matrix, and a represents the matrix itself. The value of cd is calculated using the loop:
   
        for(int i = 0; i < m; i++){
            for(int j = 0; j < n; j++){
                if(i == j){
                    cd = cd + a[i][j];
                }
            }
        }

   **Implementation/Code:** The following is the code for nmmatopstrace.cpp:

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
            double cd = 0;

            for(int i = 0; i < m; i++){
                for(int j = 0; j < n; j++){
                    cout << "Enter matrix element a" << i + 1 << j + 1 << ": ";
                    cin >> a[i][j];
                }
            }

            cout << "Tr(A) = ";
    
            for(int i = 0; i < m; i++){
                for(int j = 0; j < n; j++){
                    if(i == j){
                        cd = cd + a[i][j];
                    }
                }
            }

            cout << cd << endl;
            cout << endl;

            return 0;
        }

   **Last Modified:** November/2018
