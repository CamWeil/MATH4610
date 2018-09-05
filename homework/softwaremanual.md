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

    void machineEpsilon(float EPS)
    {
        float prev_epsilon;
    
        while ((1+EPS) != 1)
        
        {
            prev_epsilon = EPS;
        
            EPS /=2;
        }
    
        cout << "Machine Epsilon is : " << prev_epsilon << endl;
    }

    void machineEpsilon2(double EPS2)
    {
        double prev_epsilon2;
    
        while ((1+EPS2) != 1)
        
        {
            prev_epsilon2 = EPS2;
        
            EPS2 /=2;
        }
    
        cout << "Machine Epsilon is : " << prev_epsilon2 << endl;
    }

    int main()
    {
        machineEpsilon(0.5);
        machineEpsilon2(0.5);
    
        return 0;
    }

**Last Modified:** September/2018
