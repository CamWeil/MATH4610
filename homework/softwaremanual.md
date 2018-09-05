**Routine Name:**           nmmaceps

**Author:** Cam Weil

**Language:** C++

**Description/Purpose:** This routine will compute the single precision value for the machine epsilon or the number of digits
in the representation of real numbers in single precision. This is a routine for analyzing the behavior of any computer. This
usually will need to be run one time for each computer.

**Input:** There are no inputs needed in this case. Even though there are arguments supplied, the real purpose is to
return values in those variables.

**Output:** This routine returns a single precision value for the number of decimal digits that can be represented on the
computer being queried.

**Usage/Example:**

xxx

**Implementation/Code:** The following is the code for nmmaceps.cpp

    #include<iostream>
    #include <cfloat>
    using namespace std;

        void nmmaceps(float eps)
        {
            float prev_eps;
    
            while ((1+eps) != 1)
        
            {
                prev_eps = eps;
        
                eps /=2;
            }
    
            cout << "Machine Epsilon (float) is : " << prev_eps << endl;
        }

        void dnmmaceps(double deps)
        {
            double prev_deps;
    
            while ((1+deps) != 1)
        
            {
                prev_deps = deps;
        
                deps /=2;
            }
    
            cout << "Machine Epsilon (double) is : " << prev_deps << endl;
        }

        int main()
        {
            nmmaceps(0.5);
            dnmmaceps(0.5);
    
            return 0;
        }
        
**Last Modified:** September/2018
