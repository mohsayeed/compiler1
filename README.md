

# CS3320: Compilers 1


# Mini Assignment 2: Compilers and their Options

Shaik Mohammed Sayeed

CS19BTECH11004

2nd Year Undergraduate-B Tech


# Overview:

In this report we are going to analyse the features which are in common with GCC and LLVM compilers,various frontend and backend which supports these compilers,notes on the native code generated by the compilers for different architectures like x86,AMD,32-bit x86,MIPS...etc and also by comparing the compilers on various optimization levels like O0,O1,O2….as well with -Os,-Oz.


# Various Features in common compilers: GCC and LLVM.:


## GCC

GCC is a completely free software for compiling c,c++...programming and is specifically designed for GNU Operating system and named as one of the traditional compilers for compiling C,C++,Fortran,Go,D etc… and it has all the libraries which support these languages.In GCC frontend it convert the text to RTL and then it optimizes the rtl file which generates the output file(binary).GCC frontend is highly matured language,highly popular and it is widely adopted.


## LLVM

LLVM-low level virtual machine,is a compiler infrastructure technology which is used in developing the front end for any programming language and backend to develop machine code for different instruction set architecture.The main feature in the design of the clang is based on llvm and the main feature behind llvm is to use LLVM IR(intermediate representation) and it’s very similar to generation of bytecode for a java code before run time.Therefore LLVM project is a reusable compiler and also language independent and a collection of toolchain technologies.


# Front Ends that LLVM/GCC compilers support:

Front end for a compiler means which translates the source code into an intermediate state which can be pushed to the backend to churn over the IR and it optimizes the output code to produce the native machine code .
                                          Initially GCC was developed to provide a stable and highly compatible Compiler for C programming language,for the GNU system and also it was named as GNU C Compiler. As of the New latest GCC Package it supports many programming languages like **C,C++,Objective-C,Ada,Java,Go,Fortran,D** and also it supports parallel language extensions like OpenMp,OpenACC etc…
                                                              As of now LLVM supports as a compiler for many programming languages like **C,C++,Haskell ,Julia,Rust,Swift,Delphi,Go**,**Objective-C **etc using different front ends like clang which is used for C,C++ etc and many projects uses LLVM and it is the list of the projects([click here](https://llvm.org/ProjectsWithLLVM/)).


# Variation in Code Generation on Different Architectures by GCC/LLVM:

Yes we could see the difference when code is generated by the compilers like GCC/LLVM on various different architectures like x86,AMD,32-bit x86,MIPS.When we compile the hello world program using the GCC compiler on different architectures like x86_64 (standard PC),aarch64(64 bit arm) and 32bit arm.The results are when compared with the file size of the binary files produced on different architectures which are mentioned above has the following results that the file produced by standard pc x86 has 16kb,aarch64 has 521kb and arm32 has 592kb.Therefore it is highly optimized by GCC on standard PC x86 architecture.When we run the same helloworld.c program program using clang we get the size equal to 16.2kb which is almost equal to gcc output.


# Findings on different Optimizations like O0,O1,O2,O3,Os and Oz by GCC/LLVM:

O0 --->No optimization,Fastest compilation time and debuggable code

O1 --->Moderate optimization but no considerable increase in compile time

O2--->Done most optimization here

O3 --->same as O2 but parts which took longer time will be optimized. It is more powerful which does automate inline of the functions and does a higher level optimization and compilation time may increase


<table>
  <tr>
   <td>
   </td>
   <td>O0
   </td>
   <td>O1
   </td>
   <td>O2
   </td>
   <td>O3
   </td>
   <td>Ofast
   </td>
   <td>Os
   </td>
   <td>Oz
   </td>
  </tr>
  <tr>
   <td>GCC
   </td>
   <td>No opt.
   </td>
   <td>Opt bet. O0 and O2
   </td>
   <td>Done most opt.
   </td>
   <td>//ly to O2 ,do the opt. for time consuming code 
   </td>
   <td>Enables all optimization may violate language standards
   </td>
   <td>Reduces space of the binary file
   </td>
   <td>Reduces codesize further
   </td>
  </tr>
  <tr>
   <td>LLVM
   </td>
   <td>No opt.
   </td>
   <td>Opt bet. O0 and O2
   </td>
   <td>Done most opt.
   </td>
   <td>//ly to O2 ,do the opt. for time consuming code 
   </td>
   <td>Enables all optimization may violate language standards
   </td>
   <td>Reduces space of the binary file
   </td>
   <td>Reduces codesize further
   </td>
  </tr>
</table>



## Comparison between GCC and LLVM

LLVM and clang don’t depend on individual compiler parts but instead it integrates within themselves so there is a communication among themselves,here the object file is directly generated from IR itself.Where as for GCC first reads the source code then preprocess the file and make it converts into the intermediate representation then it will optimize and after all it generates the executable file. In many cases with larger codes the LLVM shows benefits when compared to GCC ,it(LLVM) reduces the compile time for the single thread execution programs by 5%.For comparison between the speed at which the program runs is relatively the GCC is good at runtime by 4 to 3 % when compared to LLVM according to researches.

We can see the results directly for runtime simulation by executing the below code 

time ./a.out then we could see the times as real ,user and sys time and we can compare the time difference between them.

On overall the clang is better than Gcc in many aspects


# References:

1.)[https://alibabatech.medium.com/gcc-vs-clang-llvm-an-in-depth-comparison-of-c-c-compilers-899ede2be378](https://alibabatech.medium.com/gcc-vs-clang-llvm-an-in-depth-comparison-of-c-c-compilers-899ede2be378)

2.)[https://stackoverflow.com/questions/24836183/what-is-the-difference-between-clang-and-llvm-and-gcc-g](https://stackoverflow.com/questions/24836183/what-is-the-difference-between-clang-and-llvm-and-gcc-g)

3.)https://gcc.gnu.org/
4.)https://github.com/mohsayeed/compiler1/

