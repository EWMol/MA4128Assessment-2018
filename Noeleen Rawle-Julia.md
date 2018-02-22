Julia Language
============================================
# Noeleen Rawle 17071844
## Parallel Computing with Julia

The majority of modern computers have more than one CPU. When several computers are combined together they are called a *cluster*. 
The speed of the CPU's and how fast they can access memory, are the two biggest factors that can influence performance. 
In Julia multiprocessing is based a messaging system, that allows programs to run multiple processses in seperate memory domains similtaneously. 
A programmer working in Julia needs to clearly manage only one of the processes in a two-process system, i.e. in Julia communication is generally one-sided.
In Julia, parallel computing is built on two primitives, which are *remote references* and *remote calls*.
Remote references come in two types: `Future` and `Remote Channel`.