# Day 02 – Linux Architecture & Under the Hood

## 1. Core Components of Linux
* **Kernel:** The core interface between the OS and physical hardware. Manages CPU, memory, drivers, and system calls.
* **User Space:** The space where user applications, user-facing utilities, and shell processes run, interacting with the kernel via system calls.
* **Init / systemd:** PID 1 (Process ID 1) initializes the user space, starts services, and manages the system boot sequence.

## 2. Process Management & States
Processes are instances of running programs tracked by a Process ID (PID). Common process states include:
* **Running (R):** Actively executing on the CPU or in the run queue.
* **Sleeping (S):** Waiting for an event, resource, or I/O operation to complete (interruptible or uninterruptible).
* **Zombie (Z):** A terminated process whose parent hasn't read its exit status yet; consumes a process table slot.
* **Stopped (T):** Paused, usually via a signal like `SIGSTOP`.

## 3. What is systemd and Why It Matters
* **Role:** The modern default init system and system manager for most Linux distributions.
* **Why it matters for DevOps:** It standardizes service management (`systemctl`), handles boot parallelization, controls resource allocations via control groups (cgroups), and automatically restarts failed background daemons to keep infrastructure reliable.

## 4. 5 Essential Daily Linux Commands for DevOps
1. `htop` / `top` – Real-time monitoring of CPU, memory utilization, and active process states.
2. `ls-a  -- to list hidden files
3. `df -h` and `du -sh` – Checking disk space availability and directory sizes to prevent storage outages.
4. `netstat -plnt – Inspecting active network sockets and listening ports to verify service binding.
5. `tail -f /var/log/syslog` – Tailing system logs live to catch real-time errors or daemon crashes.
