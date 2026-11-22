# Unix Process Communication and Prime Number Analysis

**Unit:** COMP2002 – Unix Systems Programming  
**Institution:** Curtin University  
**Year:** Semester 1, 2025  
**Project type:** Individual university assignment  
**Language and environment:** C, Unix/Linux, GCC, Make

## Overview

This is a documentation-only case study of a C program that checks whether integers are prime using parent and child processes. The program reads integers from a text file, creates one child process for each number, and uses two pipes per child to exchange a number and its primality result. The parent waits for completed children, identifies each by process ID (PID), and reports the matching result.

**The original university assignment source code is intentionally not included.** The assignment specification warns students not to release their code publicly. This repository describes the completed work without redistributing the solution.

## My work

- Implemented integer input parsing with Unix file I/O calls, including `open()`, `read()` and `close()`.
- Used `fork()` to create child processes for the input integers.
- Set up paired pipes for parent-to-child and child-to-parent communication.
- Used `write()`, `read()` and `close()` to exchange data and close unused pipe ends.
- Tracked child PIDs and used `wait()` to associate completed processes with the correct result pipe.
- Organised the project into C modules and headers, with a Makefile for building the executable.

## Demonstrated behaviour

The original submitted report includes a terminal screenshot of `make clean`, `make` and `./prime input.txt`. It shows separate child process IDs returning prime or non-prime classifications for a sample set of integers. This is **evidence from the original assignment report**, not a new execution or independent test in this portfolio.

## Skills demonstrated

C programming; Unix system calls; process creation; inter-process communication (IPC); pipes and file descriptors; PID tracking; file I/O; basic error handling; GCC and Make.

## Repository contents

- [`docs/project-case-study.md`](docs/project-case-study.md): project design, workflow, and portfolio-ready description
- [`docs/verification-and-sharing.md`](docs/verification-and-sharing.md): source limitations, validation boundaries and disclosure rules

## Scope and limitations

- The full `.c` and `.h` files and the original assignment specification are not included.
- The source code was not provided as separate files, and was **not compiled or re-run** in preparing this case study.
- The report describes the Unix process and pipe workflow; this portfolio does not claim independently measured performance, memory safety, or production readiness.
- This is an educational assignment, not a deployed service or cybersecurity attack/detection system.

## Attribution

This case study documents an individual assignment submitted by Abeda Akhter Akhi for COMP2002 at Curtin University. All observations are based on the submitted report and task specification. University-owned assessment materials and the original solution have not been included.
