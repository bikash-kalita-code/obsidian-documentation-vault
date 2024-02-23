- Concurrency is a ***concept***
	- how a program, or algorithm, is ***structured***
		- not how it is executed
		- there are different ways of executing concurrent code
- An algorithm is concurrent when it is ***structured*** into several sub parts that can be executed ***out of order*** (or **partially** ordered), without affecting the ***outcome***
	- code sections are not necessarily executed in a specific order
	- the final result remains the same

### Example
![[concurrency_example.png]]
### How are Concurrent Fragments Executed?
#### Parallel Execution
![[parallel_execution.png]]
### Time-Sliced Execution
![[time_sliced_execution.png]]
## Processes
![[processes.png]]
## Threads
![[threads.png]]
## Scheduling
![[scheduling.png]]
## Multitasking
![[multitasking.png]]
## Python Global Interpreter Lock
![[gil.png]]
## Another Approach to Multitasking
![[another_approach_to_multitasking.png]]
## Workloads
![[workloads.png]]
## CPU Bound Workloads in Python - Threading
![[cpu_bound_workloads_threading.png]]
## CPU Bound Workloads in Python - Multiprocessing
![[cpu_bound_workloads_in_python_multiprocessing.png]]


## Concurrency Introduction
- Multiprocessing
- Threading
- Asynchronous programs

- Programs we've written execute sequentially, on one CPU
- It's likely we're not making full use of the computing resources available
- It's likely we're spending a lot of time waiting for network communication
![[concurrency_introduction.excalidraw]]

