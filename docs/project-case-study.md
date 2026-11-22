# Project case study: Unix IPC and prime-number checking

## Problem

The assignment required a C program to read integers from a file and check each number for primality in a separate child process. The parent had to send the integer, receive the result, and identify which child produced the response.

## Design

**Input:** A text file whose first integer gives the count of remaining integers. The program parses the input into a one-dimensional array.

**Process creation:** A parent process creates a distinct child process for each input integer using `fork()`.

**Inter-process communication:** Two pipes are used for each child: one carries the integer from parent to child, and the other returns the primality result. Unused pipe ends are closed.

**Results:** The parent stores process IDs, waits for child termination with `wait()`, finds the matching PID, reads the result from the corresponding pipe, and prints the outcome.

**Project organisation:** The report identifies `io.c`, `io.h`, `pipe.h`, `prime_check.c`, `prime_check.h`, `prime.c`, and a Makefile.

## Evidence in the supplied report

- Pages 2–3: file reading, parsing, array size checks and integer conversion
- Pages 4–6: paired pipe design, fork/read/write flow, and descriptor handling
- Page 7: PID tracking and matching completed children with pipes
- Page 8: original terminal screenshot showing compilation and prime/non-prime output

## Key takeaways

The project offered hands-on practice in low-level Unix programming: process lifecycle management, bidirectional IPC, correct mapping of asynchronous child results, and file-descriptor management. These skills support systems programming and understanding how processes interact on Linux hosts.

## Limitations

The report supports the IPC architecture and shows an example run. The original standalone C source files were not provided in this upload, so this case study does not claim that the implementation was independently compiled, tested for memory leaks, or verified on all inputs. The assignment specification requires additional details, including `nanosleep()`; the submitted report excerpt does not independently establish all such requirements were implemented.
