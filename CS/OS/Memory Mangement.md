High level memory management functions provided by OS
1.  Used intelligently sized containers - eg. pages, segments
2. Not all memory is required at once, so act on a subset of memory
3. Provide hardware optimazation

Hardware provides support for memory allocation, arbitration. CPU comes with an MMU (Memory Management Unit) that gives out virtual addresses but it's hardware that's responsible for translating those virtual address into actual physical addresses

**Page Table**
It maintains a mapping between virtual memory address to the actual physical address in DRAM. The page size in vritual memory is same as the size of the page frame number in DRAM so the mapping table does not have to maintain a mapping for every single address, it usually maintains a mapping for the start address of the page and calculates the exact address based on the offset from the start

The OS maintains a page table for every single process and when a context switch occurs (switching processes) a new page table needs to be loaded for that new process