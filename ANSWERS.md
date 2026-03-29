# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:A thread is a smaller unit of execution inside a process that shares memory, whereas a process is an independent program with its own memory space. Compared to processes, threads have less overhead and can be created more quickly. Because threads enable improved performance and effective communication, they are employed in this assignment to imitate processes. For instance, in SchedulerSimulation, every Process object operates via a Thread.Java. This makes it possible for several processes to run simultaneously.**


[Write your answer here. Consider: What is a process? What is a thread? How do they differ in terms of memory, resources, creation overhead? Why are threads more suitable for this simulation?]

---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:Some brief processes, such as P1, P8, P9, and P10, were able to complete their initial turn due to the 4000 ms quantum. However, it took several turns (rounds) to finish longer procedures like P3 and P13. A 4000 ms quantum strikes a compromise between lowering context switching overhead and responsiveness.**

[Write your answer here. Describe the specific behavior - where does the process go? When does it run again? Give an example from your actual program output showing a process that was re-queued.]

Example from my output:
```
Efficiency Example: P1's burst time is 2599 ms. Given that $2599 was less than $4000, it completed its initial spin. According to the log, P1 completed execution without requiring a second round.Example of Preemption: P13 has a 9659 ms burst time. It was interrupted since $9659 > 4000$. According to the log, P13 had to wait two more rounds to finish before yielding CPU for context switch.

[Paste a relevant snippet from your program output here showing a process being re-queued]
```

**Explanation of example:The "Efficiency Balancer" is the Time Quantum of 4000 ms. It is tiny enough to preempt long processes, preventing the CPU from being overloaded by a single job, but large enough to enable short processes to complete in a single turn (reducing context switching overhead).**
[Explain what's happening in the output snippet you pasted]

---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:
1.New
When the simulation initializes P1 with a Priority of 0 and a Burst Time of 2599 ms, it enters the New state. Before the process control block (PCB) is added to the scheduling system, it is constructed at this point.

2. Runnable
As soon as P1 is "added to ready queue" (as seen in the first line of your report), it becomes Runnable (or Ready). It is currently loaded into memory and awaiting dispatch by the CPU scheduler.

3. Running
When the scheduler selects P1 from the queue, it enters the Running state. This is indicated by the log in your simulation:? Quantum execution by P1 [2599ms]. The CPU is actively processing P1's instructions during this stage.

4. Waiting: P1 never goes into the Waiting stage in this particular simulation. If a resource or an I/O request blocks a thread, it goes into "Waiting" mode. P1 went straight from Running to Terminated because it completed its full burst within its first CPU quantum.

5. Terminated:
When P1's "Remaining time" hits zero milliseconds, it enters the Terminated state. This is verified by the following message in your output:? P1 completed the execution. The system now reallocates its resources.**



---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: [Name of application/scenario]
Applications using Interactive User Interfaces (UI)

**Description**: 

Applications that need the system to manage several input events (keyboard input, mouse clicks) and rendering processes concurrently include word processors and web browsers.
[Describe the real-world scenario or application]

**Why Round-Robin works well here**: 
Round-Robin guarantees response. The user interface (UI) stays responsive and fluid by allocating a tiny, equal temporal slice (quantum) to each thread. It ensures that input handling consistently obtains CPU time by preventing the interface from stalling due to a single, heavy background task.
[Explain why Round-Robin scheduling is suitable. Consider fairness, responsiveness, predictability, etc.]

### Example 2: [Name of application/scenario]
Web Servers
**Description**: 
[Describe the real-world scenario or application]
Web servers that manage several client requests at once (e.g., obtaining tiny HTML files or processing API calls).

**Why Round-Robin works well here**: 
[Explain why Round-Robin scheduling is suitable. Consider fairness, responsiveness, predictability, etc.]
Round-Robin ensures equity. It guarantees that the server's CPU is not monopolized by a single client request. Instead of making some users wait endlessly while others take up the entire processor, the server makes sure that all clients receive some progress on their requests by rotating over all active requests.
---

## Summary
Important ideas I grasped from these questions:

Time Quantum: Recognizing how the quantum size directly influences the ratio of overhead to system responsiveness.

Context switching: Realizing that in order to resume unfinished processes at a later time, the scheduler must save their state to the ready queue.

Fairness: Understanding that Round-Robin is made to treat every process equally, making it perfect for interactive settings.

Ideas I should learn more about:

The trade-offs between a very small quantum (high overhead) and a very big quantum (nearing First-Come-First-Served behavior) are known as quantum optimization.

Advanced Scheduling: How to better manage critical work by integrating Round-Robin with priority-based scheduling.
1. 
2. 
