M. Masmano, I. Ripoll, A. Crespo and J. Real, "TLSF: a new dynamic memory allocator for real-time systems," Proceedings. 16th Euromicro Conference on Real-Time Systems, 2004. ECRTS 2004., Catania, Italy, 2004, pp. 79-88, doi: 10.1109/EMRTS.2004.1311009. keywords: {Real time systems;Dynamic programming;Software algorithms;Software engineering;Object oriented programming;Application software;Delay;Heuristic algorithms;Timing;Operating systems}

Proposes an algorithm for memory allocation in realtime systems. Size classes are segregated by coarseness, with one data structure representing power of two size classes and a second representing linear interpolation within a power of two window. Two level indirection may add overhead but overall promising. Also has a good summary of segmented free list algorithms

---
Detlefs, D.; Dosser, A.; Zorn, B. (June 1994). "Memory allocation costs in large C and C++ programs" (PDF). Software: Practice and Experience. 24 (6): 527–542. CiteSeerX 10.1.1.30.3073. doi:10.1002/spe.4380240602. S2CID 14214110.

Benchmarks malloc and free performance for a number of different compilers running real code. The number of instruction cycles is counted. A little outdated and doesn't really mention custom algorithms/allocator implementation details. Mentions a deferred/garbage collected allocator.

---
Richard Jones, Antony Hosking, and Eliot Moss. 2011. The Garbage Collection Handbook: The Art of Automatic Memory Management (1st. ed.). Chapman & Hall/CRC.

Memory allocation chapter gives a good overview of the topic. Discusses internal & external fragmentation, segregated free lists, memory alignment/padding, multithreaded considerations etc. Presents some fairly sophisticated tree based algorithms such as cartesian trees where entries have two dimmensional keys (spatial location and size).

---
"Main Storage Allocation" (PDF). IBM Operating System/360 Concepts and Facilities (PDF). IBM Systems Reference Library (First ed.). IBM Corporation. 1965. p. 74. Retrieved Apr 3, 2019.

An interesting historical note on how memory allocation used to work.

---
Jonathan Bartlett. "Inside Memory Management". IBM DeveloperWorks. https://developer.ibm.com/tutorials/l-memory/

Tutorial on how one might go about reimplementing malloc. Includes code and instructions on how to compile to a shared library and replace malloc. Also references Knuth for classic algorithms and modern c++ small object allocators. Broadly compares some methods in terms of ease to implement as well as performance and flexibility.

---
 alloca(3) – Linux Programmer's Manual – Library Functions. https://manned.org/alloca.3

 alloca is linux's function for stack allocation. Incredibly fast, simply involves manipulating the stack pointer, but limited in size.

 ---
 Donald Knuth. Fundamental Algorithms, Third Edition. Addison-Wesley, 1997. ISBN 0-201-89683-4. Section 2.5: Dynamic Storage Allocation, pp. 435–456.

 Classic memory allocation algorithms. Outdated but forms the basis for many later developments.

 ---
 M.S. Johnstone and P.R. Wilson. The Memory Fragmentation Problem: Solved ? In Proc. of the Int. Symposium on Memory Management (ISMM’98), Vancouver, Canada. ACM Press, 1998.

Studied as an academic problem with synthetic test cases, memory fragmentation is severe. However studies up to this point have not investigated whether synthetic test cases are able to predict real code performance. This paper examines a number of memory allocators running production code and concludes that real test cases produce low to no fragmentation.

 ---
 T. Ogasawara. An algorithm with constant execution time for dynamic storage allocation. 2nd Int. Workshop on Real-Time Computing Systems and Applications, page 21, 1995

 Proposes "Half Fit", an alorithm with a measurable worst case execution time, which outperforms binary buddy allocation. Interestingly, the algorithm can find a free block without searching a free list or tree.

---
Dhruv Matani, Gaurav Menghani "Fast Bitmap Fit: A CPU Cache Line friendly memory allocator for single object allocations", https://arxiv.org/pdf/2110.10357

Many memory allocators are optimised for speed of allocation and deallocation, but don't necessarily take into account cache locality of random allocations. This makes little difference when slabs of memory are allocated to hold multiple objects, but when each allocation is for a single object the locality becomes important. This paper proposes a method which is elegant yet cache aware.

---
Masmano, M., Ripoll, I., Real, J., Crespo, A. and Wellings, A.J. (2008), Implementation of a constant-time dynamic storage allocator. Softw: Pract. Exper., 38: 995-1026. https://doi.org/10.1002/spe.858

Improves on the standard bitmap allocation technique.

---
Dirk Grunwald, Benjamin Zorn, and Robert Henderson. 1993. Improving the cache locality of memory allocation. SIGPLAN Not. 28, 6 (June 1993), 177–186. https://doi.org/10.1145/173262.155107

Measures execution time of real C++ programs running various allocators. Concludes that spatial locality has a measurable effect on program speed.

---

C. J. Stephenson "Fast fits" https://dl.acm.org/doi/pdf/10.1145/800217.806613

Proposes a tree structure for finding a suitable block. Based on cartesian trees.

---
Jean Vuillemin. 1980. A unifying look at data structures. Commun. ACM 23, 4 (April 1980), 229–239. https://doi.org/10.1145/358841.358852

Presents a number of combinatorial/geomatric data structures, among them is the cartesian tree, a two dimensional generalisation of binary search tree.

---
Daniel Dominic Sleator and Robert Endre Tarjan. 1985. Self-adjusting binary search trees. J. ACM 32, 3 (July 1985), 652–686. https://doi.org/10.1145/3828.3835

Introduces splay trees and analyses their amortised performance.

---

Overleaf, Australian English

Loose intro (why is memory important, affects on performance (idling), historical memory cost), Definition of problem (ram, cache, standard basis, von neumann architecture, early memory management, virtual memory), common terminology, history. Over time, how has malloc research been informed. Describe