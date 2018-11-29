12c. **Routine Name:**           nmvecnormlinf

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will compute and return the l<sub>∞</sub> norm (length) of a given vector of arbitrary length.
   
   **Input:** There are inputs needed for the length of the vector and the elements of the vector. These inputs are both prompted for at the beginning of the routine.

   **Output:** This routine simply calculates the maximum magnitude of all the elements of the vector, which is then given as the output. For example:
   
        Enter vector length: 3
        Enter coordinate #1 for vector v: 1
        Enter coordinate #2 for vector v: 2
        Enter coordinate #3 for vector v: 3
        l∞-norm = 3.

   **Usage/Example:** The routine defines one double variable, linf, as well as an int variable, n, and a vector with double elements, v. n represents the length of the vector, linf represents the l<sub>∞</sub> norm of the vector, and v represents the vector itself. The l<sub∞</sub> norm is calculated using the loop:
   
        for(vector<double>::size_type i = 0; i < n; i++){
            if(fabs(v[i]) > linf){
                linf = fabs(v[i]);
            }
        
            else{
                linf = linf;
            }
        }

   **Implementation/Code:** The following is the code for nmvecnormlinf.cpp:

        #include<iostream>
        #include<math.h>
        #include<vector>
        using namespace std;

        int n;
        double linf = 0;

        int main(){
            cout << "Enter vector length: ";
            cin >> n;

            vector<double> v(n);

            for(vector<double>::size_type i = 0; i < n; i++){
                cout << "Enter coordinate #" << i + 1 << " for vector v: ";
                cin >> v[i];
            }

            for(vector<double>::size_type i = 0; i < n; i++){
                if(fabs(v[i]) > linf){
                    linf = fabs(v[i]);
                }
        
                else{
                    linf = linf;
                }
            }
    
            cout << "l∞-norm = " << linf << "." << endl;

            return 0;
        }

   **Last Modified:** November/2018
