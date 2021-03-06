02. **Routine Name:**           nmqproots

   **Author:** Cam Weil

   **Language:** C++

   **Description/Purpose:** This routine will compute the roots of a quadratic polynomial. This is a routine for solving any equation of the form ax<sup>2</sup> + bx + c so long as a ≠ 0.

   **Input:** There are inputs needed for a, b, and c, which are prompted for at the beginning of the routine.

   **Output:** This routine returns the two roots to the solution x = (-b ± √(b<sup>2</sup> - 4ac))/(2a). For example, the inputs a = 1, b = 2, and c = 3 will return the output:
  
        x1 = -1 + 1.41421i
        x2 = -1 - 1.41421i

   **Usage/Example:** The routine defines eight float variables, a, b, c, x1, x2, disc, xreal, and ximag. a, b, and c are the coefficients of the polynomial and disc is the discriminant of the polynomial, which is given as:

        disc = b*b - 4*a*c;
   
   The value of the discriminant is used to determine how the roots of the polynomial should be calculated. If the discriminant is positive or zero, then the roots are real and are given as:
   
        x1 = (-b + sqrt(disc))/(2*a);
        x2 = (-b - sqrt(disc))/(2*a);
        
   If the discriminant is negative, then the roots are complex and are given as:
   
        xreal = -b/(2*a);
        ximag = sqrt(-disc)/(2*a);

  This is necessary to ensure that the routine never has to take the square root of a negative number, which would otherwise return an undefined value. It is also worth noting that if the discriminant is zero, then x1 and x2 will return identical values.

   **Implementation/Code:** The following is the code for nmqproots.cpp:

        #include<iostream>
        #include<math.h>
        using namespace std;

        int main(){

        float a, b, c, x1, x2, disc, xreal, ximag;

            cout << "Enter coefficient a: ";
            cin >> a;
    
                if(a == 0){
                    cout << "a cannot be 0. Enter coefficient a: ";
                    cin >> a;
                }
    
            cout << "Enter coefficient b: ";
            cin >> b;
            cout << "Enter coefficient c: ";
            cin >> c;
    
            disc = b*b - 4*a*c;
    
                if(disc >= 0){
                    x1 = (-b + sqrt(disc))/(2*a);
                    x2 = (-b - sqrt(disc))/(2*a);
                    cout << "x1 = " << x1 << endl;
                    cout << "x2 = " << x2 << endl;
                }
    
                else{
                    xreal = -b/(2*a);
                    ximag = sqrt(-disc)/(2*a);
                    cout << "x1 = " << xreal << " + " << ximag << "i" << endl;
                    cout << "x2 = " << xreal << " - " << ximag << "i" << endl;
                }

            return 0;
    
        }
        
   **Last Modified:** November/2018
