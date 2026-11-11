# Assignment 10: Memory Management and Paging in xv6

## Overview

### Question 1 — Memory Management: Tracking Physical Memory Allocation
- **Brief:** Modifies `kalloc()` and `kfree()` in `kalloc.c` to track physical page allocation and deallocation counters. Implements the `memstats()` system call to report total allocated, freed, active, and available physical pages. Includes a test program (`memtest.c`) to verify stats using `sbrk()`.

### Question 2 — Virtual Memory: Virtual-to-Physical Address Translation
- **Brief:** Implements the `vtop(int virtual_address)` system call utilizing `walkpgdir()` in `vm.c` to translate virtual addresses to physical addresses. It validates page table entry presence, extracts physical frame numbers, and combines them with page offsets. Tested via `vttest.c` with valid and unmapped virtual addresses.

### Question 3 — Paging: Page Table Management and Page Protection
- **Brief:** Adds `pageinfo()` to query page mapping and flags (`P`, `W`, `U`), alongside `setreadonly()` to clear the `PTE_W` write bit on target pages. Demonstrates page protection in `pagetest.c` by modifying permissions of an allocated page and attempting a write to trigger a page fault.

### Question 4 — Page Replacement Algorithms: FIFO, LRU, and Optimal
- **Brief:** Implements user program `pagereplace.c` to simulate FIFO, LRU, and Optimal page replacement algorithms against a given reference string. Evaluates algorithm behavior across frame sizes of 3, 4, and 5. Generates a comparison table highlighting hit/fault counts, hit ratios, and page fault ratios to identify the best-performing policy.