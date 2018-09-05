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

???

**Implementation/Code:** The following is the code for nmmaceps.cpp

    #include<iostream>
    #include <cfloat>
    using namespace std;

        void nmmaceps(float eps)
        {
            float preveps;
    
            while ((1+eps) != 1)
        
            {
                preveps = eps;
        
                eps /= 2;
            }
    
            cout << "Machine Epsilon (float) is : " << preveps << endl;
        }

        void nmdmaceps(double deps)
        {
            double prevdeps;
    
            while ((1+deps) != 1)
        
            {
                prevdeps = deps;
        
                deps /= 2;
            }
    
            cout << "Machine Epsilon (double) is : " << prevdeps << endl;
        }

        int main()
        {
            nmmaceps(0.5);
            nmdmaceps(0.5);
    
            return 0;
        }
        
**Last Modified:** September/2018
