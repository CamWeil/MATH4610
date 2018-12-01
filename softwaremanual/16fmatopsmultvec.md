16f. **Routine Name:**           nmmatopsmultvec

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will compute and return the product of a matrix and a vector (A * x).
   
   **Input:** There are inputs needed for the size of the matrix, the elements of the matrix, and the elements of the vector. These inputs are all prompted for at the beginning of the routine.

   **Output:** This routine simply calculates the product of a matrix and a vector by the rules of matrix multiplication, which is then given as the output. For example:
   
        Enter matrix size (number of rows): 2
        Enter matrix size (number of columns): 2
        Enter matrix element a11: 1
        Enter matrix element a12: 2
        Enter matrix element a21: 3
        Enter matrix element a22: 4
        Enter coordinate #1 for vector x: 1
        Enter coordinate #2 for vector x: 2
        A * x = < 5  11 >

   **Usage/Example:** The routine defines two int variables, m and n, and two vectors with double elements, x and cf, as well as a matrix with double elements, a. m and n represent the rows and columns of the matrix, respectively, x represents the vector, cf represents the product of the vector and the matrix, and a represents the matrix itself. The value of cf is calculated using the loop:
   
        for(int i = 0; i < m; i++){
            for(int j = 0; j < n; j++){
                cf[i] = cf[i] + x[j]*a[i][j];
            }
        }

   **Implementation/Code:** The following is the code for nmmatopsmultvec.cpp:

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
            vector<double> cf(m);
            vector<double> x(n);

            for(int i = 0; i < m; i++){
                for(int j = 0; j < n; j++){
                    cout << "Enter matrix element a" << i + 1 << j + 1 << ": ";
                    cin >> a[i][j];
                }
            }
            
            for(vector<double>::size_type i = 0; i < n; i++){
                cout << "Enter coordinate #" << i + 1 << " for vector x: ";
                cin >> x[i];
            }

            cout << "A * x = <";
    
            for(int i = 0; i < m; i++){
                for(int j = 0; j < n; j++){
                    cf[i] = cf[i] + x[j]*a[i][j];
                }
                cout << " " << cf[i] << " ";
            }

            cout << ">" << endl;
            cout << endl;

            return 0;
        }

   **Last Modified:** November/2018
