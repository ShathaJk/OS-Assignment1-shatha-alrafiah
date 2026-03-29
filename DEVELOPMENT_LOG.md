# Development Log

## Instructions
Document your development process as you work on the assignment. Add entries showing:
- What you worked on
- Problems you encountered 
- How you solved them
- Time spent

**Requirements**: Minimum 5 entries showing progression over time.

---

## Example Entry Format:

### Entry 1 - [April 1, 2026, 2:30 PM]
**What I did**: Forked the repository and set up my student ID
**Details**: 
- Created GitHub account with university email
- Forked the starter repository
- Changed student ID on line 92 to my actual ID (441234567)
- Compiled and ran the program successfully
**Challenges**: Had to install JDK first because javac wasn't recognized
**Solution**: Downloaded JDK 17 from Oracle website and set PATH variable
**Time spent**: 30 minutes

---

## Your Development Log:

### Entry 1 - [March 25, 2026, 8:52 PM]
**What I did**: Initial Setup and Student ID Configuration.
**Details**: 
Configured the simulation with my unique Student ID: 445052018.
Verified the base parameters: 15 processes and a 4000ms Time Quantum.
Initialized the repository and confirmed the environment was ready for execution.
**Challenges**:Ensuring the random seed generated from my ID produced the correct burst times.
**Solution**:
Validated the output against the expected initial process list (P1 to P15).
**Time spent**: 
40 minutes
---

### Entry 2 - [March 27, 2026, 9:58 PM]
**What I did**: 
Implementation of Feature 2: Context Switch Tracking System.
**Details**: 
Developed the logic to monitor when a process exceeds its 4000ms quantum.
Implemented the "yield" mechanism that moves unfinished processes (like P2, P3, etc.) to the back of the Ready Queue.
Added visual logs to show the "Remaining Time" after each context switch.
**Challenges**: 
Correcting the logic where a process should not yield if its remaining time is exactly 0ms.
**Solution**: 
Added a conditional check to verify completion before triggering the context switch.
**Time spent**: 
1 hour 30 minutes
---

### Entry 3 - [March 27, 2026, 10:35 PM]
**What I did**: Implementation of Feature 3: Waiting Time Calculation and Summary.
**Details**: Added the logic to calculate how long each process stayed in the Ready Queue.
Created the final summary table to display individual and average waiting times.
Automated the "Overall Progress" calculation for each thread.
**Challenges**: Keeping track of total elapsed time to accurately subtract burst time from turnaround time.
**Solution**: 
Implemented a global timer variable that increments with every CPU cycle/quantum.
**Time spent**: 
1 hour
---

### Entry 4 - [March 29, 2026, 6:54 PM]
**What I did**: Reflection and Multi-threading Concepts Revision.
**Details**: Revised the reflection answers regarding multithreading concepts.
Documented the challenges faced with shared resources and thread synchronization during the simulation.
**Challenges**: Explaining the difference between "Parallelism" and "Concurrency" in the context of this RR scheduler.
**Solution**: Refined the definitions to show that RR simulates concurrency on a single core.
**Time spent**: 
1 hour
---

### Entry 5 - [March 29, 2026, 7:46 PM]
**What I did**: Final Revision of ANSWERS.md
**Details**: Updated detailed explanations for Thread vs. Process, Ready Queue behavior, and Thread States (P1 trace).
Finalized the real-world application examples (Web Servers and UI).
Ensured all LaTeX formatting and technical terms were consistent throughout the document.
**Challenges**: : None.
**Solution**: Final proofread to ensure the ID 445052018 is present on all relevant pages.
**Time spent**: 
50 minutes
---

### Entry 6 - [Optional - Date and Time]
**What I did**: 

**Details**: 

**Challenges**: 

**Solution**: 

**Time spent**: 

---

## Summary

**Total time spent on assignment**: [5 hours 30 minutes]

**Most challenging part**: Implementing the Context Switch Tracking System and ensuring the Ready Queue state was preserved accurately across multiple cycles.

**Most interesting learning**: Seeing the lifecycle of P1 versus P13—how one finishes instantly while the other highlights the "fairness" of Round-Robin through multiple context switches.

**What I would do differently next time**: 
I would add a feature to dynamically adjust the Time Quantum during the simulation to compare performance metrics in real-time.
