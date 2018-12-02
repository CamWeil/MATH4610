Homework 3


1a. [Vector Norm Software Manual Entry (l<sub>1</sub>)](https://github.com/CamWeil/math4610/blob/master/softwaremanual/10avecnorml1.md)

1b. [Vector Norm Software Manual Entry (l<sub>2</sub>)](https://github.com/CamWeil/math4610/blob/master/softwaremanual/10bvecnorml2.md)

1c. [Vector Norm Software Manual Entry (l<sub>∞</sub>)](https://github.com/CamWeil/math4610/blob/master/softwaremanual/10cvecnormlinf.md)

2a. [Absolute and Relative Vector Errors Software Manual Entry (l<sub>1</sub>)](https://github.com/CamWeil/math4610/blob/master/softwaremanual/11avecerrl1.md)

2b. [Absolute and Relative Vector Errors Software Manual Entry (l<sub>2</sub>)](https://github.com/CamWeil/math4610/blob/master/softwaremanual/11bvecerrl2.md)

2c. [Absolute and Relative Vector Errors Software Manual Entry (l<sub>∞</sub>)](https://github.com/CamWeil/math4610/blob/master/softwaremanual/11cvecerrlinf.md)

3a. [Vector Operation Software Manual Entry (Vector Addition)](https://github.com/CamWeil/math4610/blob/master/softwaremanual/12avecopsadd.md)

3b. [Vector Operation Software Manual Entry (Vector Subtraction)](https://github.com/CamWeil/math4610/blob/master/softwaremanual/12bvecopssub.md)

3c. [Vector Operation Software Manual Entry (Scalar Multiplication)](https://github.com/CamWeil/math4610/blob/master/softwaremanual/12cvecopsmultsc.md)

3d. [Vector Operation Software Manual Entry (Inner Product)](https://github.com/CamWeil/math4610/blob/master/softwaremanual/12dvecopsdot.md)

3e. [Vector Operation Software Manual Entry (Cross Product)](https://github.com/CamWeil/math4610/blob/master/softwaremanual/12evecopscross.md)

4a. [Matrix Norm Software Manual Entry (l<sub>1</sub>)](https://github.com/CamWeil/math4610/blob/master/softwaremanual/13amatnorml1.md)

4b. [Matrix Norm Software Manual Entry (Frobenius)](https://github.com/CamWeil/math4610/blob/master/softwaremanual/13bmatnormfrob.md)

4c. [Matrix Norm Software Manual Entry (l<sub>∞</sub>)](https://github.com/CamWeil/math4610/blob/master/softwaremanual/13cmatnormlinf.md)

5a. [Matrix Operation Software Manual Entry (Matrix Addition)](https://github.com/CamWeil/math4610/blob/master/softwaremanual/14amatopsadd.md)

5b. [Matrix Operation Software Manual Entry (Matrix Subtraction)](https://github.com/CamWeil/math4610/blob/master/softwaremanual/14bmatopssub.md)

5c. [Matrix Operation Software Manual Entry (Matrix Transpose)](https://github.com/CamWeil/math4610/blob/master/softwaremanual/14cmatopstransp.md)

5d. [Matrix Operation Software Manual Entry (Matrix Trace)](https://github.com/CamWeil/math4610/blob/master/softwaremanual/14dmatopstrace.md)

5e. [Matrix Operation Software Manual Entry (Scalar Multiplication)](https://github.com/CamWeil/math4610/blob/master/softwaremanual/14ematopsmultsc.md)

5f. [Matrix Operation Software Manual Entry (Vector Multiplication)](https://github.com/CamWeil/math4610/blob/master/softwaremanual/14fmatopsmultvec.md)

5g. [Matrix Operation Software Manual Entry (Matrix Multiplication)](https://github.com/CamWeil/math4610/blob/master/softwaremanual/14gmatopsmultmat.md)

6a. [Matrix Operation Software Manual Entry (Kronecker Product)](https://github.com/CamWeil/math4610/blob/master/softwaremanual/14hmatopskron.md)

6b. [Matrix Operation Software Manual Entry (Kronecker Product)](https://github.com/CamWeil/math4610/blob/master/softwaremanual/14hmatopskron.md)

6c. [Matrix Operation Software Manual Entry (Matrix Determinant)](https://github.com/CamWeil/math4610/blob/master/softwaremanual/14imatopsdet.md)

7. N/A

8a. [Vector Operation Software Manual Entry (Inner Product)](https://github.com/CamWeil/math4610/blob/master/softwaremanual/12dvecopsdot.md)

8b. [Vector Operation Software Manual Entry (Cross Product)](https://github.com/CamWeil/math4610/blob/master/softwaremanual/12evecopscross.md)

9. [Orthogonal/Orthonormal Basis Software Manual Entry](https://github.com/CamWeil/math4610/blob/master/softwaremanual/15orthbasis.md)

10. Problem: Perform an online search using the term Kronecker product. Find sites that describe the product and applications of the Kronecker product. Write up a paragraph or two describing this topic citing at least three web pages and/or web sites.

    Answer: Given a field F, the Kronecker product of two matrices is defined as <b>A</b> ⊗ <b>B</b> = \[a<sub>ij</sub>B\] for any matrices <b>A</b> = \[a<sub>ij</sub>\] ∈ F<sup>m x n</sup> and B ∈ F<sup>p x q</sup>. One application for the Kronecker product is the continuous Lyapunov equation AX + XA<sup>H</sup> = Q, respectively, with Q being a Hermitian matrix and A<sup>H</sup> being the Hermitian transpose of A. This equation is used in certain branches of control theory, such as stability analysis and optimal control, and it can be solved for using the Kronecker product in the equation \[(A<sup>T</sup> ⊗ I) + (I ⊗ A<sup>H</sup>)\]vec(X) = vec(Q), which has a unique solution X if and only if A<sup>H</sup> and −A<sup>T</sup> have no shared eigenvalues. For more practical usage, the Kronecker product can also be used to solve the commutativity equation AX - XA = 0 by rewriting it as \[(I ⊗ A) - (A<sup>T</sup> ⊗ I)\]vec(X) = 0, which is simply a null space problem.
    
    Source: On the Kronecker Products and Their Applications. (2013, June 06). Retrieved November 14, 2018, from https://www.hindawi.com/journals/jam/2013/296185/
    
    Lyapunov equation. (2018, November 06). Retrieved November 14, 2018, from https://en.wikipedia.org/wiki/Lyapunov_equation
    
    On the Kronecker Product. (2013, August 01). Retrieved November 14, 2018, from https://www.math.uwaterloo.ca/~hwolkowi/henry/reports/kronthesisschaecke04.pdf
