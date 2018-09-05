Homework 1

[Calculus/Differential Equations Solutions](https://github.com/CamWeil/math4610/blob/master/homework/nmhw1.pdf)

Problem: Write a code that will return machine precision for your computer (or any other computer for that matter) in single precision arithmetic. Give the method a name that is descriptive. For example, maceps(), or something like that. The routine should return the default machine precision. Create a second routine that will return the machine precision in double precision computations. Give the routine a unique name, say dmaceps(). Make sure that your code is fully documented with you as the author and so on. An example of a Fortran code is included in this repository. You can translate this into a Python, C, or C++ code to do the work. You can also modify the Fortran and use this directly.

Problem: Create a repository on [Github](https://www.github.com) and create a repositry for this homework that will contain a software manual for all the code you will write and work with in the course. The repository should include a table of contents where each entry in the table of contents is linked to a software manual page where the user can read about that entry. Start the software manual by creating software manual pages for the two routines using the template at the following link:
Software Manual Markdown Template
Note: The software manual must use the template above to be graded!.
Problem: To complete this problem, you may need to go to the Engineering Computer Lab on the third floor of the Engineering Building. If you have Cygwin installed on a laptop or desktop computer that you own, you can do this homework at home. Note that if you have some version of Linux/Unix on your computer, you can also do this homework using your own computer. Finally, if you are working on a MAC/Apple, you can also complete this problem using your laptop or desktop. Complete the following steps:
Log onto a computer (Engineering Lab) and open a command terminal to work in.
Upload/copy the routines that you created in the first problem.
Compile the routines into object modules (.o files). For example, put the files you have uploaded into a folder, say hw1_prob3, using the command
            % mkdir hw1_prob3
          
and in a Cygwin/Linux/Unix operating system. Note that the "%" is the command prompt that may appear in the command terminal. Then use
            % mv *.f hw1_prob3
            % cd hw1_prob3
          
to move all files ending with a .f suffix to the folder just created and change the working folder to the folder just created. Finally, compile the files using
            % gfortran -c *.f
          
or
            % gcc -c *.c
          
using the C-compiler in Cygwin. The result will be a bunch of object files with a suffix of ".o".
The last step in this problem is to create a shared library from the routines you have created.
            % ar rcv mylib *.o
          
or
            % ar rcv mylib *.o
            % ranlib mylib.a
          
Problem: In this problem you will learn a bit more about your computer and how many processes you can run on the cores included in your computer. You will use OpenMP to do this work.
To start, write code like the following.
            program main
            print *, "hello world!"
            stop
            end
          
to implement the good old Hello World introductory program. Compile and run the code you have created. The code should produce the string in the print statement. That is,
            hello world!
          
Now, let's do a bit more with this example. We will need to add some code to the example to have each of the cores on your computer write out the same statement. In addition, the way that the code is compiled will also change. That we will do on the other side of the following code.
            |      program main
            |      integer id, nthrds
            |      integer omp_get_thread_num, omp_get_num_threads
            |C$OMP PARALLEL PRIVATE(id)
            |      id = omp_get_thread_num()
            |      print *, 'hello world from thread', id
            |C$OMP BARRIER
            |      if(id .eq. 0) then
            |        nthrds = omp_get_num_threads()
            |        print *, 'There are', nthrds, ' threads!'
            |      end if
            |C$OMP END PARALLEL
            |      stop
            |      end
          
First, there are some things that need to be described in the code:
The line on the left indicates how the code needs to be written in the column. In fortran, the comment line must start as the first character of the line typed in. So, the pipe, "|", is like the edge of the window and is not actually a character on your screen, just the border of the document.
The string "C$OMP" tells the compiler that the line is a line associated with OpenMP. The first letter must appear in the first column and indicates that when compiled without OpenMP extensions, will be ignored. If the OpenMP library is available, the compiler will include the parameters contained in the comments. These strings are the start of a "directive" to the compiler to do something.
For the present time, (1) save the code above into a file named "hello.f", (2) compile the code above, using
                % gfortran -fopenmp hello.f -o hello
              
and then run the compiled version of the code using the command
                % ./hello.exe
              
Report the results of running the code.
