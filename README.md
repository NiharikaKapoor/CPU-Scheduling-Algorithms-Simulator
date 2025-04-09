# CPU Scheduling Simulator

## Overview
The **CPU Scheduling Simulator** is a tool designed to simulate and analyze various CPU scheduling algorithms used in operating systems. It provides a detailed implementation of both preemptive and non-preemptive scheduling techniques, enabling users to compare their performance and gain insights into their behavior.

---

## Features

### Supported Scheduling Algorithms
1. **First-Come-First-Serve (FCFS)**  
   Non-preemptive scheduling based on the order of arrival.
2. **Round Robin (RR)**  
   Preemptive scheduling with a fixed quantum.
3. **Shortest Process Next (SPN)**  
   Non-preemptive scheduling prioritizing the shortest burst time.
4. **Shortest Remaining Time (SRT)**  
   Preemptive version of SPN.
5. **Highest Response Ratio Next (HRRN)**  
   Non-preemptive scheduling based on the response ratio.
6. **Aging**  
   Scheduling that increases process priority over time to prevent starvation.

### Key Metrics
- **Finish Time**: When a process completes execution.
- **Turnaround Time**: Total time a process spends in the system.
- **Normalized Turnaround Time**: Ratio of turnaround time to service time.

### Visual Timeline
- Displays the execution and waiting periods of each process in a tabular format.

### Operation Modes
1. **Trace Mode**: Step-by-step visualization of scheduling.
2. **Statistics Mode**: Summary of algorithm performance with metrics.

---

## Project Structure

### Files
1. **main.cpp**  
   Contains the main logic for the simulator, including the implementation of scheduling algorithms.
2. **parser.h**  
   Handles input parsing and initialization of data structures.
3. **Makefile**  
   Automates the build process for compiling and linking the project.

---

## Input Format
The simulator reads input from the console in the following format:

```
<operation> <algorithms> <last_instant> <process_count>
<process_name>,<arrival_time>,<service_time>
...
```

### Example Input
```
TRACE 1,2-3 10 3
P1,0,5
P2,1,3
P3,2,8
```

### Explanation
- **Operation**: `TRACE` or `STATS`.
- **Algorithms**: `1` (FCFS), `2-3` (RR with quantum=3).
- **Last Instant**: Total simulation time.
- **Process Count**: Number of processes.
- **Processes**: Each process defined by name, arrival time, and service time.

---

## Output

### Trace Mode
Displays the timeline of execution and waiting periods for each process.

### Statistics Mode
Provides metrics such as:
- Finish Time
- Turnaround Time
- Normalized Turnaround Time

---

## How to Build and Run

### Build
1. Ensure you have a C++ compiler installed (e.g., `g++`).
2. Use the provided **Makefile**:
   ```bash
   make
   ```

### Run
1. Execute the compiled binary:
   ```bash
   ./lab4
   ```
2. Provide input as specified in the format.

---

## Example Execution

### Input
```
TRACE 1,2-3 10 3
P1,0,5
P2,1,3
P3,2,8
```

### Output (Trace Mode)
```
Time:       0 1 2 3 4 5 6 7 8 9
------------------------------------------------
P1     |* * * * *|         |
P2     |         |* * *    |
P3     |         |    * * *|
------------------------------------------------
```

### Output (Statistics Mode)
```
Algorithm: FCFS
Process    |  P1  |  P2  |  P3  |
Arrival    |   0  |   1  |   2  |
Service    |   5  |   3  |   8  |
Finish     |   5  |   8  |  16  |
Turnaround |   5  |   7  |  14  |
NormTurn   | 1.00 | 2.33 | 1.75 |
```

---

## Contact
For any queries or suggestions, please contact:
- **Email**: [niharikakapoor864@gmail.com]

---

## License
This project is open-source and available under the [MIT License](https://opensource.org/licenses/MIT).

