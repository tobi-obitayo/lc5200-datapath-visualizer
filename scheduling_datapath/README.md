# CPU Scheduler Visualizer

An interactive CPU process scheduling visualizer built for CS 2200 — simulates six scheduling algorithms with a tick-by-tick SVG timeline, per-process statistics, and step-through navigation.

🔗 **[Live Demo](https://tobi-obitayo.github.io/lc5200-datapath-visualizer/scheduling_datapath/scheduling_datapath.html)**

---

## What It Does

Configure up to 5 processes (CPU burst 1, I/O burst, CPU burst 2, priority, arrival time), pick a scheduling algorithm, and click Run. The visualizer produces:

- **Gantt-style SVG timeline** — color-coded per process, with CPU and I/O rows
- **Hover tooltips** — show burst number and remaining time for any cell
- **Statistics table** — finish time, turnaround, and waiting time per process, plus averages
- **Step-through mode** — navigate tick by tick with Prev/Next buttons or ← → arrow keys; a red highlight column tracks the current tick and an event log shows what happened each cycle
- **Compare view** — runs all 6 algorithms simultaneously and displays compact timelines side by side for easy comparison
- **Export** — download the current timeline as SVG or PNG (2× retina resolution)
- **LocalStorage** — process configurations are saved automatically and restored on next visit

---

## Algorithms

| Algorithm | Type | Description |
|---|---|---|
| **FCFS** | Non-preemptive | Runs processes in arrival order |
| **SJF** | Non-preemptive | Always picks the shortest remaining burst next |
| **SRTF** | Preemptive | Preempts the running process if a shorter job arrives |
| **Round Robin** | Preemptive | Fixed time quantum, rotates through the ready queue |
| **Priority (Preemptive)** | Preemptive | Higher priority number = higher priority; preempts on arrival |
| **Priority (Non-Preemptive)** | Non-preemptive | Highest priority selected at dispatch; runs to burst completion |

---

## Process Fields

| Field | Description |
|---|---|
| **CPU Burst 1** | First CPU execution phase (ticks) |
| **I/O Burst** | I/O wait phase between CPU bursts (ticks) |
| **CPU Burst 2** | Second CPU execution phase (ticks) |
| **Priority** | Scheduling priority (higher number = higher priority) |
| **Arrival** | Tick at which the process enters the system |

---

## Controls

| Input | Action |
|---|---|
| Run | Simulate with current settings |
| Randomize | Generate random burst times and arrival offsets |
| ⓘ button | Toggle algorithm description banner |
| ← / → arrow keys | Step backward / forward one tick (in step-through mode) |
| Settings → Compact view | Toggle between compact (CPU + I/O rows) and separated (one row per process) |
| Settings → Concurrent I/O | Toggle between CS 2200 serial I/O queue and real-world concurrent I/O |
| Settings → Step-through mode | Enable tick-by-tick navigation with event log |
| Settings → Compare all algorithms | Run all 6 algorithms side by side |
| Settings → Export | Download timeline as SVG or PNG |
| Reset | Restore default process configuration |

---

## Why I Built This

Scheduling algorithms are straightforward on paper but harder to reason about when processes have different arrival times, I/O phases, and preemption rules. This visualizer makes the tick-by-tick behavior concrete — especially useful for comparing how FCFS, SRTF, and Priority handle the same workload.

---

## Tech Stack

- Vanilla HTML, CSS, JavaScript
- No dependencies — runs entirely in the browser
- Single self-contained file

---

## Contributing

The repo is public — feel free to open issues or PRs for additional algorithms, bug fixes, or UI improvements.
