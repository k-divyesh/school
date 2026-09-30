# Introduction to Systems Programming

## system:

- a core of a computer is it's operating system
- this course is about the operating system **unix**

## Bare Metal Programming

- before operating systems, we ran programs directly on hardware
- flaws:
  - The program has to be written for specific hardware
  - The program must manage hardware components
  - The program must manage all the tasks
  - i.e., a lot of extra work

## Benifits of Operating Systems

- Let programs focus on specific tasks, operating systems manages the hardware so the program can focus on it's task.
- new program != rewrite everything

## Operating Systems

- An operating system is responsibile for _managing a computer's hardware_
- Allows programs to:
  - share resources
  - interact with devices
  - basically a resource manager, managing:
    - processes
    - memory
    - the file system
    - input and output

- example of resources sharing: cpu time sharing
- process behaves as if it has the machine to itself
- slows individual processes but system is faster all together
- process "idle time" allows for this

## Linux

- A version of unix created by Linus Torvalds
- extended to many architectures cpu types
- many distros and free under GNU general public license

## Parts of Unix OS

- Utitlities: standard tools/apps
- _Shell_: interface between user and kernel
- _Kernel_: manages processes, resources, hardware

## Computer:

- an electronic device aware of only high and low eelectrical charges(1 or 0)
- series of on/off(binary code) makes an instruction

## Levels of Programming Languages

1. Direct Machine Code - _Binary_
2. Assembly Code
3. High-Level Code (C, go, rust, etc.)

## Translating Levels

- A _compiler_ transforms code from one level to another
- An _interpreter_ translates and exectues generic byte code instructions to specific machine code instructions

## Compiling in C

Source Code &rarr; OS specific compiler &rarr; OS specific code &rarr; OS output

## Interpreting in Python/java _todo_

Source Code &rarr; compiler &rarr; byte code &raar; interpreter translates into os specific code &rarr; OS output

## C

- intended to be as powerful and efficient as assembly lvl languages
- structured to make code easy to read and write
- standardization allows for easy portablility
- used in everything
- popular in data analytics due to efficiency
- embedded systems often use C
