---
layout: page
title: Projects
permalink: /projects/
---

### [Universal Data Guard for Intel SGX](https://github.com/nes77/udg-sgx) 
  I've been working with Professor Emin Gun Sirer on a program which would allow for authenticated manipulation of program state via the Ethereum blockchain. Security is achieved via the Intel Software Guard Extensions, an ISA extension for x86-64 which allows programs to execute in isolation from the rest of the system, including other hardware and the OS.

  The biggest challenges with this project are working in a RAM-constrained environment, and working without OS support. RAM availability is in the order of 32-64 MB, while typical Ethereum clients rely on having more than 2 GB of RAM available. This leads to significant optimization and decisions on feature trade-offs to ensure that the program can accomplish everything with only a small percentage of normally available memory. Lack of OS support means no direct file or network I/O, and a significantly reduced standard library. I have had to reimplement, substitute, or simply do without a significant number of library features, including support for arbitrarily-sized integer operations. This also meant rewriting a significant amount of code which could normally have been copied from a regular Ethereum client, due to either a dependency or assumption of the presence of significantly more resources.

  The program is written in C++11.

***

### [Pixielang](https://github.com/nes77/pixielang)
  Pixielang is intended to be an interpreted, dynamically-typed language which compiles to bytecode (or Pixiecode). The intention is for the bytecode to be semantically rich enough for some verification of program behavior to take place before any code is run. The bytecode would consist of a core set of simple instructions which would exist on any typical stack-based virtual machine in addition to a more complex, multi-byte set of instructions encompassing things like file and network I/O. This would allow for users to grant or deny programs permission to perform certain tasks, as well as informing them of all the things a program is capable of doing based on its source code. For example, a simple examination of a program's use of network I/O instructions would reveal if it were designed to send data over the internet, or to whom, if the destination were specified at compile-time.

  Not much progress has been made on this project; I am working towards settling on a final language design and feature set, after which I plan to implement the runtime, and then a compiler. I anticipate the primary problems to come from the implementation of the runtime; interpreted languages are already typically slow, and the design of the bytecode runs the risk of being even slower due to the multi-byte design.

  I have not settled on a language for implementation of the runtime, though I am leaning towards C++ or Go: C++, for its performance and vast array of libraries; and Go for its "batteries included" design, acceptable performance, and comparable simplicity to C++, as well as the built-in concurrency available.

***

## Other Projects

### Godit -- A Go API for Reddit

  The current state of Go language libraries for accessing Reddit API's is fairly dismal, given the relative sparsity and obsolescence of implementations. Considering Go's orientation towards server and distributed program implementation, it seems like a perfect candidate for implementing bots designed to handle large amounts of data from the website. My hope is to provide a PRAW-like interface for interacting with the service, and ensuring that Go bots for Reddit obey the Reddit API rules.
   
## Contact me

[me@nicksamson.com](mailto:me@nicksamson.com)
