17. **Routine Name:**           nmmorthbasis

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will compute and return an orthonormal basis from a general basis in two dimensions.
   
   **Input:** There are inputs needed for the elements of the two vectors, which are prompted for at the beginning of the routine.

   **Output:** This routine simply performs the Gram-Schmidt procedure on the two inputted vectors to determine an orthogonal and an orthonormal set vectors, which are then given as the output. For example:
 
        Enter coordinate #1 for general vector v1: 1
        Enter coordinate #2 for general vector v1: 2
        Enter coordinate #1 for general vector v2: 3
        Enter coordinate #2 for general vector v2: 4
        Orthogonal vector u1 = < 1 2 >.
        Orthogonal vector u2 = < 0.8 -0.4 >.
        Orthonormal vector e1 = < 0.447214 0.894427 >.
        Orthonormal vector e2 = < 0.894427 -0.447214 >.

   **Usage/Example:** The routine defines three double variables, dotuv, dotuu1, and dotuu2, as well as seven vectors with double elements, v1, v2, u1, u2, e1, e2, and projuv. dotuv, dotuu1, and dotuu2 represent the inner products of u1 and v2, u1 and u1, and u2 and u2, respectively. v1 and v2 represent the inputted general basis, whereas u1 and u2 represent the calculated orthogonal vectors and e1 and e2 represent the calculated orthonormal vectors, which are calculated using the loops:
   
        u1 = v1; 
    
        for(vector<double>::size_type i = 0; i < 2; i++){
            dotuv = dotuv + u1[i]*v2[i];
            dotuu1 = dotuu1 + u1[i]*u1[i];
        }

        for(vector<double>::size_type i = 0; i < 2; i++){
            e1[i] = (u1[i])/(sqrt(dotuu1));
        }

        for(vector<double>::size_type i = 0; i < 2; i++){
            projuv[i] = ((dotuv)/(dotuu1))*u1[i];

        }

        for(vector<double>::size_type i = 0; i < 2; i++){
            u2[i] = v2[i] - projuv[i];

            if(u2[i] == 0){
                cout << "Error: Vectors v1 and v2 are linearly dependent." << endl;
                return 0;
            }
        }

        for(vector<double>::size_type i = 0; i < 2; i++){
            dotuu2 = dotuu2 + u2[i]*u2[i];
        }

        for(vector<double>::size_type i = 0; i < 2; i++){
            e2[i] = (u2[i])/(sqrt(dotuu2));
        }

   **Implementation/Code:** The following is the code for nmorthbasis.cpp:

        #include<iostream>
        #include<math.h>
        #include<vector>
        using namespace std;

        vector<double> v1(2);
        vector<double> v2(2);
        vector<double> u1(2);
        vector<double> u2(2);
        vector<double> e1(2);
        vector<double> e2(2);
        double dotuv;
        double dotuu1;
        double dotuu2;
        vector<double> projuv(2);

        int main(){
            for(vector<double>::size_type i = 0; i < 2; i++){
                cout << "Enter coordinate #" << i + 1 << " for general vector v1: ";
                cin >> v1[i];
            }

            for(vector<double>::size_type i = 0; i < 2; i++){
                cout << "Enter coordinate #" << i + 1 << " for general vector v2: ";
                cin >> v2[i];
            }

            u1 = v1;

            for(vector<double>::size_type i = 0; i < 2; i++){
                dotuv = dotuv + u1[i]*v2[i];
                dotuu1 = dotuu1 + u1[i]*u1[i];
            }

            for(vector<double>::size_type i = 0; i < 2; i++){
                e1[i] = (u1[i])/(sqrt(dotuu1));
            }

            for(vector<double>::size_type i = 0; i < 2; i++){
                projuv[i] = ((dotuv)/(dotuu1))*u1[i];

            }

            for(vector<double>::size_type i = 0; i < 2; i++){
                u2[i] = v2[i] - projuv[i];

                if(u2[i] == 0){
                    cout << "Error: Vectors v1 and v2 are linearly dependent." << endl;
                    return 0;
                }
            }

            for(vector<double>::size_type i = 0; i < 2; i++){
                dotuu2 = dotuu2 + u2[i]*u2[i];
            }

            for(vector<double>::size_type i = 0; i < 2; i++){
                e2[i] = (u2[i])/(sqrt(dotuu2));
            }

            cout << "Orthogonal vector u1 = < ";

            for(vector<double>::size_type i = 0; i < 2; i++){
                cout << u1[i] << " ";
            }

            cout << ">." << endl;

            cout << "Orthogonal vector u2 = < ";

            for(vector<double>::size_type i = 0; i < 2; i++){
                cout << u2[i] << " ";
            }

            cout << ">." << endl;

            cout << "Orthonormal vector e1 = < ";

            for(vector<double>::size_type i = 0; i < 2; i++){
                cout << e1[i] << " ";
            }

            cout << ">." << endl;

            cout << "Orthonormal vector e2 = < ";

            for(vector<double>::size_type i = 0; i < 2; i++){
                cout << e2[i] << " ";
            }

            cout << ">." << endl;

            return 0;
        }

   **Last Modified:** November/2018
