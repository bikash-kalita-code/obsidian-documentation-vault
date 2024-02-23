## What is Process Scheduling?
**Process Scheduling** is an OS task that schedules processes of different states like ready, waiting, and running.
Process scheduling allows OS to allocate a time interval of CPU execution for each process. Another important reason for using a process scheduling system is that it keeps the CPU busy all the time. This allows you to get the minimum response time for programs.
### Process Scheduling Queues
Process Scheduling Queues help you to maintain a distinct queue for each and every process states and PCBs. All the process of the same execution state are placed in the same queue. Therefore, whenever the state of a process is modified, its PCB needs to be unlinked from its existing queue, which moves back to the new state queue.

Three types of operating system queues are:
1. **Job queue** – It helps you to store all the processes in the system.
2. 