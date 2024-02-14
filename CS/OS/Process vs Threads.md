A process is represented by a data structure known as a Process Control Block (PCB). The PCB contains various pieces of information
* Process State - watiting, running, idle etc
* Program counter (PC) - The pointer/address of the next instruction to be executed by the CPU
* Static data - Address of the actual code under execution, static variables, list of open files etc
* Stack Pointer - Points to the address of the stack variables
* Registers - What registers are currently being used by the process
* Address Space - defines the address space/layout of the process that contains all of the above information and contains the mappings of the virtual address --> physical address of all of the data

Each process gets its own Address space and exectuion context. A thread has its own execution context but shares common state (Address space, static data) with other threads. Therefore, multi-threaded programming has lower memory requirements than multi-processing and lower context switching overhead as the Address space is shared and hence is more efficient. 

**Caveat**: Since multiple threads share data, we need to be careful about the data access which could lead to inconsistencies. Concepts like Mutex (Mututal exclusion) and Semaphores help to solve that problem.

Birrell's paper on pThreads (good introduction): https://s3.amazonaws.com/content.udacity-data.com/courses/ud923/references/ud923-birrell-paper.pdf

