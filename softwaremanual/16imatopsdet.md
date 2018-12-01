16i. **Routine Name:**           nmmatopsdet

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will compute and return the determinant of a square matrix that is no larger than 3 x 3 (det(A)).
   
   **Input:** There are inputs needed for the size of the matrix and the elements of the matrix. These inputs are both prompted for at the beginning of the routine.

   **Output:** This routine simply calculates the determinant of a matrix by its definition depending on the size of the matrix, which is then given as the output. For example:
   
        Enter matrix size (number of rows): 2
        Enter matrix size (number of columns): 2
        Enter matrix element a11: 1
        Enter matrix element a12: 2
        Enter matrix element a21: 3
        Enter matrix element a22: 4
        det(A) = -2

   **Usage/Example:** The routine defines one int variable, n, and a double variable, ci, as well as an array with double elements, a. n represents the size of the matrix, ci represents the determinant of the matrix, and a represents the matrix itself. The value of ci is calculated using the statements:
   
        if(n <= 3){
            if(n == 1){
                ci = a[0][0];
            }

            else if(n == 2){
                ci = a[0][0]*a[1][1] - a[0][1]*a[1][0];
            }

            else{
                ci = a[0][0]*(a[1][1]*a[2][2] - a[1][2]*a[2][1]) - a[0][1]*(a[1][0]*a[2][2]
                - a[1][2]*a[2][0]) + a[0][2]*(a[1][0]*a[2][1] - a[1][1]*a[2][0]);
            }
        }

   **Implementation/Code:** The following is the code for nmmatopsdet.cpp:

        #include<iostream>
        #include<math.h>
        #include<vector>
        using namespace std;

        int n;

        int main(){

            cout << "Enter matrix size: ";
            cin >> n;

            double a[n][n];
            double ci = 0

            for(int i = 0; i < n; i++){
                for(int j = 0; j < n; j++){
                    cout << "Enter matrix element a" << i + 1 << j + 1 << ": ";
                    cin >> a[i][j];
                }
            }
            
            cout << "det(A) = ";
   
            if(n <= 3){
                if(n == 1){
                    ci = a[0][0];
                    cout << ci << endl;
                }

                else if(n == 2){
                    ci = a[0][0]*a[1][1] - a[0][1]*a[1][0];
                    cout << ci << endl;
                }

                else{
                    ci = a[0][0]*(a[1][1]*a[2][2] - a[1][2]*a[2][1]) - a[0][1]*(a[1][0]*a[2][2]
                    - a[1][2]*a[2][0]) + a[0][2]*(a[1][0]*a[2][1] - a[1][1]*a[2][0]);
                    cout << ci << endl;
                }
            }
 
            cout << endl;

            return 0;
        }

   **Last Modified:** November/2018
