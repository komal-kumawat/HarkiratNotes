# 🖥️ Process Management (Operating System)

## 📌 What is a Process?

A **process** is a program that is currently running.

Example:

* When you open Chrome → a process is created
* When you run `node app.js` → a process is created

---

# 📌 What is Process Management?

> **Process Management** is the function of the Operating System (OS) that handles creation, execution, scheduling, and termination of processes.

The OS decides:

* Which process runs
* For how long
* When to pause it
* When to stop it

---

# 🔄 Process Life Cycle

![Image](https://miro.medium.com/1%2ALdafsmbCdfR882Vtd1Kp0g.jpeg)

![Image](https://www.cs.uic.edu/~jbell/CourseNotes/OperatingSystems/images/Chapter3/3_02_ProcessState.jpg)

![Image](https://www.researchgate.net/publication/332546783/figure/fig3/AS%3A749937696464896%401555810488119/Process-state-transition-diagram.png)

![Image](https://i.imgur.com/YvsaPHI.jpg)

A process goes through these states:

### 1️⃣ New

Process is being created.

### 2️⃣ Ready

Waiting in queue to get CPU.

### 3️⃣ Running

Currently executing on CPU.

### 4️⃣ Waiting / Blocked

Waiting for I/O (like file read, network response).

### 5️⃣ Terminated

Process has finished execution.

---

# 🧠 What Does OS Do in Process Management?

## 1️⃣ Process Creation

* When you open an app
* OS assigns:

  * PID (Process ID)
  * Memory
  * CPU time

---

## 2️⃣ Scheduling

OS decides which process gets CPU.

Types of scheduling:

* FCFS (First Come First Serve)
* Round Robin
* Priority Scheduling

---

## 3️⃣ Context Switching

When CPU switches from one process to another.

OS:

* Saves current process state
* Loads next process state

---

## 4️⃣ Process Termination

When:

* Program finishes
* User kills process
* Error occurs

---

# 🔹 Important Concepts

### ✅ PCB (Process Control Block)

Stores:

* Process ID
* State
* CPU registers
* Memory info

---

### ✅ Multitasking

Running multiple processes by switching CPU quickly.

---

### ✅ Parent & Child Process

Example:

* When you run a command in terminal
* It creates a child process

---

# 🔧 Linux Commands Related to Process

| Command    | Use                     |
| ---------- | ----------------------- |
| `ps`       | Show running processes  |
| `top`      | Live process monitoring |
| `kill PID` | Stop process            |
| `htop`     | Advanced process viewer |

---

# 🎯 Interview Definition

> Process management is the operating system function that handles creation, scheduling, execution, and termination of processes while efficiently allocating CPU and memory resources.

---

Great 🚀 These are **very important OS interview topics**.
Let’s explain each clearly and in detail.

---

# 🧵 1️⃣ Thread vs Process

## 📌 Process

* A program in execution
* Has its own **memory space**
* Heavyweight
* Slower to create

Example: Opening Chrome

---

## 📌 Thread

* Smallest unit of execution inside a process
* Shares memory with other threads
* Lightweight
* Faster to create

Example: One tab loading, one downloading, one playing video

---

## 📊 Comparison Table

| Feature       | Process                                 | Thread                                   |
| ------------- | --------------------------------------- | ---------------------------------------- |
| Memory        | Separate memory                         | Shared memory                            |
| Communication | IPC (slow)                              | Shared variables (fast)                  |
| Creation Time | Slow                                    | Fast                                     |
| Isolation     | High                                    | Low                                      |
| Crash Impact  | One process crash doesn’t affect others | One thread crash may crash whole process |

---

## 🔄 Diagram

![Image](https://static.afteracademy.com/images/what-is-a-thread-in-os-and-what-are-the-differences-between-a-process-and-a-thread-single-threaded-and-multiple-threaded-process-83d094ff508aaf5f.jpg)

![Image](https://www.tutorialspoint.com/operating_system/images/thread_processes.jpg)

![Image](https://miro.medium.com/v2/resize%3Afit%3A1400/1%2AWE3CYOftAKC4V_GhKUOecA.png)

![Image](https://assets.bytebytego.com/diagrams/0304-program-process-thread.png)

---

# 🧟 2️⃣ Zombie Process

## 📌 What is it?

> A zombie process is a process that has finished execution but still exists in the process table.

It has:

* Completed execution
* But parent hasn’t collected its exit status

So it stays as **defunct (zombie)**.

---

## 🧠 Why It Happens?

When:

1. Child process finishes
2. Parent does NOT call `wait()`
3. OS keeps entry in process table

---

## 🔍 How to See Zombie (Linux)

```
ps aux
```

Zombie processes show as:

```
Z
```

---

## ⚠️ Why It’s Problem?

* Uses process table entry
* Too many zombies → system issue

---

## 🛠️ Fix

Parent must call:

```
wait()
```

Or kill parent process.

---

# 🔐 3️⃣ Deadlock

## 📌 Definition

> Deadlock is a situation where two or more processes wait forever for each other to release resources.

---

## 🧠 Simple Example

Process A holds Resource 1
Process B holds Resource 2

A waits for Resource 2
B waits for Resource 1

👉 Both stuck forever ❌

---

## 🔄 Diagram

![Image](https://www.cs.fsu.edu/~baker/cop5611.S03/graphics/basicdeadlock2.gif)

![Image](https://www.cs.uic.edu/~jbell/CourseNotes/OperatingSystems/images/Chapter7/7_09_TwoGraphs.jpg)

![Image](https://image.slidesharecdn.com/circularwait-141025033831-conversion-gate02/75/Circular-wait-Operating-Systems-4-2048.jpg)

![Image](https://www.researchgate.net/publication/321746639/figure/fig3/AS%3A570605079666688%401513054260738/state-diagram-of-circular-wait-condition.png)

---

## 📌 4 Necessary Conditions of Deadlock

1. Mutual Exclusion
2. Hold and Wait
3. No Preemption
4. Circular Wait

If all four occur → Deadlock happens.

---

## 🛠️ Solutions

* Avoid deadlock
* Detect and recover
* Banker’s Algorithm

---

# ⚙️ 4️⃣ CPU Scheduling Algorithms (Detailed)

CPU Scheduling decides **which process gets CPU next**.

---

## 1️⃣ FCFS (First Come First Serve)

📌 Process that arrives first runs first.

✔ Simple
❌ Long waiting time

Example:

```
P1 → P2 → P3
```

---

## 2️⃣ SJF (Shortest Job First)

📌 Process with shortest burst time runs first.

✔ Minimum average waiting time
❌ Hard to predict burst time

---

## 3️⃣ Round Robin (RR)

📌 Each process gets fixed time slice (quantum).

Example:

```
Time quantum = 2ms
P1 → P2 → P3 → P1 → P2
```

✔ Fair
✔ Good for time-sharing systems

---

## 4️⃣ Priority Scheduling

📌 Process with highest priority runs first.

✔ Important tasks run early
❌ Low priority may starve

---

## 5️⃣ Multilevel Queue

Separate queues for:

* System processes
* User processes

---

## 📊 Scheduling Diagram

![Image](https://www.researchgate.net/publication/236346423/figure/fig7/AS%3A668422832656399%401536375830943/Gantt-Chart-Of-Different-Schedules-for-Scenario-A-Min-Min-LBIMM-PA-LBIMM-Algorithm.ppm)

![Image](https://scaler.com/topics/images/working-of-round-robin-scheduling-in-os.webp)

![Image](https://www.researchgate.net/publication/278783147/figure/tbl5/AS%3A667599742447630%401536179590787/the-Gantt-chart-for-SJF-is-presented-thus.png)

![Image](https://i.sstatic.net/Zoql6.png)

---

# 🎯 Interview Quick Answers

### Thread vs Process

Process is independent program; thread is execution unit inside process sharing memory.

### Zombie Process

A terminated child process whose parent hasn’t collected exit status.

### Deadlock

A situation where processes wait forever for each other’s resources.

### CPU Scheduling

Method used by OS to decide which process gets CPU.

---
