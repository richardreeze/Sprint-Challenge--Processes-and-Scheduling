1. List all of the main states a process may be in at any point in time on a standard Unix system. Briefly explain what each of these states mean.
- Created: When a process is first created.
- Ready: When a process has been loaded into memory and is awaiting execution on a CPU.
- Running: When a process is chosen for execution. It can run in one of two modes (kernel mode or user mode).
- Blocked: When a process cannot carry on without an external change in state or event ocurring.
- Terminated: When a process completes its execution or is explicitly killed.

2. What is a Zombie Process? How does it get created? How does it get destroyed?
- This gets pretty dark, but here goes.
When a child process has completed execution but still needs its parent process to read its exit status, it becomes a zombie process.
To destroy the zombie, the parent needs to read the exit status via the `wait` system call. Once that's done, the zombie entry is removed from the process table and it is said to be "reaped."

3. Describe the job of the Scheduler in the OS in general.
- Whenever you tell your computer to do something, someone has to assign the resources for it to happen. That 'someone' is the scheduler.

4. Describe the benefits of the MLFQ over a plain Round-Robin scheduler.
- The MLFQ addresses two problems: optimize turnaround time (it runs shorter jobs first) and minimize response time (which makes the system feel responsive to users). Round-Robin reduces response time but is terrible for turnaround time.
