14e. **Routine Name:**           nmvecopscross

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will compute and return the cross product of two vectors with length three (v1 x v2).
   
   **Input:** There are inputs needed for the elements of the two vectors, which are prompted for at the beginning of the routine.

   **Output:** This routine simply calculates the cross product of two vectors, which is then given as the output. For example:
 
        Enter coordinate #1 for vector v1: 1
        Enter coordinate #2 for vector v1: 2
        Enter coordinate #3 for vector v1: 3
        Enter coordinate #1 for vector v2: 4
        Enter coordinate #2 for vector v2: 5
        Enter coordinate #3 for vector v2: 6
        v1 x v2 = < -3  -6  -3 >.

   **Usage/Example:** The routine defines three vectors with double elements, v1, v2, and v3e, where v3e represents the cross product of the two vectors, and v1 and v2 represent the vectors themselves. The values of v3e are calculated manually as:
   
        v3e[0] = v1[1]*v2[2] - v1[2]*v2[1];
        v3e[1] = v1[0]*v2[2] - v1[2]*v2[0];
        v3e[2] = v1[0]*v2[1] - v1[1]*v2[0];

   **Implementation/Code:** The following is the code for nmvecopscross.cpp:

        #include<iostream>
        #include<math.h>
        #include<vector>
        using namespace std;

        int main(){
            vector<double> v1(3);
            vector<double> v2(3);
            vector<double> v3e(3);

            for(vector<double>::size_type i = 0; i < 3; i++){
                cout << "Enter coordinate #" << i + 1 << " for vector v1: ";
                cin >> v1[i];
            }

            for(vector<double>::size_type i = 0; i < 3; i++){
                cout << "Enter coordinate #" << i + 1 << " for vector v2: ";
                cin >> v2[i];
            }
            
            cout << "v1 x v2 = <";

            v3e[0] = v1[1]*v2[2] - v1[2]*v2[1];
            v3e[1] = v1[0]*v2[2] - v1[2]*v2[0];
            v3e[2] = v1[0]*v2[1] - v1[1]*v2[0];

            for(vector<double>::size_type i = 0; i < n; i++){
                cout << " " << v3e[i] << " ";
            }

            cout << ">." << endl;

            return 0;
        }

   **Last Modified:** November/2018
