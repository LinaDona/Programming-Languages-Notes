# High Performance Programming
- High performance == optimal use of computing resources
- MIMD: distributed architecture
- more transistors per area but a limit on freq (heat problem) ==> use of more cores ==> parallel arch/prog

## Flynn Classification
In this classification, it is assumed that a stream of intsructions **process**(?) a stream of data inside a processing unit.   
1. SISD: single core, each instruction has access to only one data to process. addition of two numbers in one clock cycle.
2. SIMD: treat multiple data in parallel, most computers from 1990 till now has this architecture. PU does one single operation but on multiple data (vector for exp) ==> addition of vectors (matrix computation) in one clock cycle.
3. MISD (theoritical): multiple operations on a single data.
4. MIMD: multiple units treat multiple data.

### Examples
1. SISD: old CPUs.
2. SIMD: GPU (it's not really a specialized PU, especially nowadays, it's considered general purpose); CPU (MMX, SSE, ```AVX``` for Intel, ```NEON``` for ARM) technologies, in this case, the technology is a part of the Instruction Set (assembly code), not outsider thing like GPU.    
exp: an instruction that is capable of treating 256 bytes, can operate on 4 integers in one clock cycle.
3. doesn't exist.
4. MIMD: **Multi-core CPUs**: each core treats multiple data;   
**Distributed systems**: they are a set of computers that can be seen virtually as a single computer. 
exp: google searches are not done by a single server, rather 1000s of them. The process of "eliminating collisions/handling results from servers" is load balancing: one guy (server) will balance the load across many servers. they are heterogenous and can be found in different geographical areas. They are general purpose; **GRID Computing**: (China vs USA); within one motherboard, nbr of possible cores are limited, max ~128; scientific revolved not GP. They usually exist in the same space (the processor units).


### Note
In phones, the ARM RISC processors that are usually found do not process (decode) videos. That is done by a hard coded decoder.     
There are no DSPs on phones. DSPs do not understand high level languages, only binary.

### Server CPUs
they are multi-core CPUs. Entry level ones do not need to have that many cores, and servers who host IO bound processes do not need very high performance cores. It all depends on what kind of job the server does. 
### Execution time calculation
```
time ./prog.exe
```
### OpenCL
is middle-ware. Not like CUDA for Nvidia. It helps us programming for Nvidia GPUs and Intel GPUs. 

### Commands
On linux (or Unix machines) the information about your cpu is in ```/proc/cpuinfo```.  
You can extract information from there by hand, or with a grep command:  
```grep flags /proc/cpuinfo```. 

This command tells you whether you have AVX on your processor or not. It will print the available *technologies* for each core you have and highlight ```avx``` and ```avx2```.
```
    grep avx /proc/cpuinfo 
```
You can also just display the content of ```/proc/cpuinfo```:
```
    cat /proc/cpuinfo
```