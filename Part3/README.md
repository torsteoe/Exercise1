# Reasons for concurrency and parallelism


To complete this exercise you will have to use git. Create one or several commits that adds answers to the following questions and push it to your groups repository to complete the task.

When answering the questions, remember to use all the resources at your disposal. Asking the internet isn't a form of "cheating", it's a way of learning.

 ### What is concurrency? What is parallelism? What's the difference?
 > Parallelism: When two tasks are run at the exact same time. 
 
   Concurrency: This is when two tasks overlap, they are not necessarily running at the same time, but take advantage of wait states
 
 ### Why have machines become increasingly multicore in the past decade?
 > One obtains better performance without increasing clock frequency, and this can reduce power consumption (heat losses, leakage current is reduced) 
 
 ### What kinds of problems motivates the need for concurrent execution?
 (Or phrased differently: What problems do concurrency help in solving?)
 > Lost update: two simultaneous events, where one must be completely done before the other for example
   Uncommited data: Rollback happens after data has been read by one task so rollback in fact does "not happen"
   Inconsistent retrievals: Some data is updated by task B while task A is reading (so his data is not coherent).
 
 ### Does creating concurrent programs make the programmer's life easier? Harder? Maybe both?
 (Come back to this after you have worked on part 4 of this exercise)
 > 
 
 ### What are the differences between processes, threads, green threads, and coroutines?
 > 
 Processes are managed by the OS and are truly concurrent. They exist within their own address space.
 
 Threads are also managed by the OS, but within the same address space as parent and other threads. Multi-tasking is pre-emptive, possibly truly concurrent
 
 green threads are managed by the user, not the OS
 
 Coroutines are cooperatively multitasking and are not truly concurrent, not managed by the OS
 ### Which one of these do `pthread_create()` (C/POSIX), `threading.Thread()` (Python), `go` (Go) create?
 > They create a coroutine.
 
 ### How does pythons Global Interpreter Lock (GIL) influence the way a python Thread behaves?
 > Prevents threads from executing python code bytes simultaneously
 
 ### With this in mind: What is the workaround for the GIL (Hint: it's another module)?
 > multiprocessing module 
 
 ### What does `func GOMAXPROCS(n int) int` change? 
 > This changes the number of threads. 
