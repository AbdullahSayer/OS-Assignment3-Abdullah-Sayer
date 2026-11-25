# 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

> This is the **only file** your instructor reads to grade Parts 3 and 4 (documentation and video). Everything you write here must be **in your own words**.

---

## 🛑 STOP: Read This Before You Do Anything Else

> ### 1️⃣ Read the whole `README.md` first
> The `README.md` in this repository contains the full instructions: how this assignment continues Assignment 1, the Chapter 5 recap, class descriptions, feature specifications, question prompts and the video script. **If you skip it, you will lose marks.**
>
> ### 2️⃣ Understand the full code before answering any question
> Open `SchedulerSimulationSync.java` and read it **from top to bottom**. You must be able to explain what `SharedStats`, `ReadyQueue`, `CpuWorker`, `RaceWindow.pause()`, `ReentrantLock` and `Semaphore` do **before** you write a single answer in Parts B and C. **Run the original starter first** (it is intentionally broken) and **save its output**: you need it for Question 1 of Part C.
>
> ### 3️⃣ Use only the code of this repository
> Work **only** on `SchedulerSimulationSync.java` from this repository. Do **not** copy or paste code from your previous assignments.
>
> ### 4️⃣ Commit many times, not once
> A single commit, or all commits made in the last hour, costs you **-0.5 mark**. See the [Commit Rules](#-commit-rules-mandatory) below.

**How to use this file:**
1. Fill in your **Student Information** (below) right now.
2. Follow the steps in the **Work Roadmap** in order.
3. Update the **Development Log** *every time* you work on the assignment, not at the end.
4. Do not delete any section header. Replace the `[...]` placeholders with your own text.

---

## 👤 Student Information

> ⚠️ **WARNING:** Fill this in first. Your name and ID must match the student ID you set in `SchedulerSimulationSync.java` (line 304) and the one you say in your video.

| Field | Your Answer |
|-------|-------------|
| **Full Name** | Abdullah Sayer Almutairi |
| **Student ID** | 445350082 |
| **University Email** | 445350082@std.psau.edu.sa |
| **GitHub Username** | AbdullahSayer |
| **Repository Link** | https://github.com/AbdullahSayer/OS-Assignment3-Abdullah-Sayer |
 
---

## 🎥 Video Link

**Video Link**: https://drive.google.com/file/d/1uJDB7Ef34kqHz8BckKY4Neubv991u9dV/view?usp=sharing

> ⚠️ **WARNING:** The video must be **publicly accessible** ("Anyone with the link can view") on **Google Drive**, **YouTube (Unlisted or Public)** or any other cloud file-sharing system. A private, restricted or broken link counts as a **missing video (-1 mark)**.
>
> 💡 **TIP:** Open the link in a **private/incognito window** before you submit. If it asks you to log in or request access, it is not public.
>
> 📌 **NOTE:** The link goes in **this file only** (`MY_WORK.md`), **not** in `README.md`. Name your video file `StudentID_Assignment3_Demo.mp4`. It must last **2 to 3 minutes**.

---

## 🗺️ Work Roadmap (follow in this order)

| Step | What to do | Where | Marks |
|:----:|------------|-------|:-----:|
| 0 | Read `README.md`, read the full code, **run the original starter and save its output** (it fails on purpose) | Your IDE | – |
| 1 | Fork, rename, keep the repo **PUBLIC**, set your student ID (line 304), **commit** | GitHub + code | Part 1 (1) |
| 2 | Feature 1: Mutex lock on the ready queue, **commit** | Code | Part 2 (0.25) |
| 3 | Feature 2: Mutex lock(s) on the shared statistics, **commit** | Code | Part 2 (0.25) |
| 4 | Feature 3: Counting semaphore instead of busy waiting, **commit** | Code | Part 2 (0.5) |
| 5 | Development Log (5+ entries, different dates) | This file, Part A | Part 3 (0.5) |
| 6 | Reflection (4 questions) | This file, Part B | Part 3 (0.5) |
| 7 | Technical Answers (4 questions) | This file, Part C | Part 3 (0.5) |
| 8 | Record the video, upload it, paste the link above | Video + this file | Part 4 (1.5) |
| 9 | Final check, then submit the repo link on Blackboard | Blackboard | – |

> 💡 **TIP:** Tick each step off as you go. Do not leave the log, the reflection or the video for the last day.

---

## 🔁 Commit Rules (MANDATORY)

> ### ⚠️ MANY COMMITS ARE REQUIRED. A single bulk commit is penalized (-0.5 mark).

**Minimum: 4 meaningful commits. Aim for 7 or more.**

| # | Commit | Example message |
|:-:|--------|-----------------|
| 1 | Student ID set | `Set my student ID: 441234567` |
| 2 | Feature 1: Ready queue lock | `Feature 1: Protected the ready queue with a ReentrantLock` |
| 3 | Feature 2: Statistics locks | `Feature 2: Added locks to the shared statistics counters` |
| 4 | Feature 3: Semaphore | `Feature 3: Replaced busy waiting with a counting semaphore` |
| 5 | Development log entries | `Docs: Added development log entries 1-3` |
| 6 | Reflection and answers | `Docs: Completed reflection and technical answers` |
| 7 | Video link | `Docs: Added demo video link` |

**Rules:**
- ✅ **One commit per feature.** Do not put all three features in one commit.
- ✅ **Commit after each work session**, and after each part of this file.
- ✅ **Spread your commits over different dates.** Not all in one day.
- ❌ **Do not make all commits in the last hour** before the deadline (November 14, 2026).
- ❌ **No vague messages** like `done`, `update` or `final version`.

> 💡 **TIP:** Your commit history is checked and you **show it in your video** (at least 4 commits visible). Your development log dates should match your commit dates.
>
> 💡 **TIP:** **Use VS Code** (see *Recommended Development Environment* in `README.md` for the full setup). Sign in to GitHub in VS Code, then commit from the Source Control panel (Ctrl+Shift+G) → stage → write a message → Commit → Sync/Push. You can edit and commit this file the same way. **Pushing** matters: commits that are not pushed to GitHub are invisible to the instructor.

---

# Part A: Development Log (0.5 mark)

> ⚠️ **WARNING:** Minimum **5 entries**, spread over **different dates**. Five entries written on the same day, or written all at once at the end, will lose marks and look like a copy. Entry dates should be **between the start of the assignment and the deadline (November 14, 2026)**.
>
> 💡 **TIP:** Write an entry at the **end of each work session**, while you still remember what happened. It takes 5 minutes.
>
> 💡 **TIP:** Be specific. "Worked on the code" is a weak entry. "Added a `ReentrantLock queueLock` to `ReadyQueue` and wrapped the body of `poll()` in `lock()` / `try` / `finally { unlock() }`" is a strong one.
>
> 📌 **NOTE:** Each entry needs: date and time, what you did, details, challenges, solution, and time spent. Real challenges are fine (and expected). Do not invent fake ones.

## Example Entry (do not copy it, write your own)

### Entry 1 - [November 2, 2026, 4:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter

**Details**:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`

**Challenges**: I did not understand why the same process was picked by three CPUs

**Solution**: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it

**Time spent**: 45 minutes

---

## Your Development Log

> Draft for review: the dates and time ranges below are the estimates supplied by the student. The saved screenshots and messages show setup and testing on November 24, 2026; check the dates and times against the actual work and Git history before submitting. Do not backdate entries.

### Entry 1 - November 24, 2026, 3:03–3:34 PM
**What I did**: Set up the project and changed my student ID.

**Details**:
- Forked the starter repository and renamed it.
- Cloned my repository and opened the Java file in NetBeans.
- Changed the student ID in `SchedulerSimulationSync.java`.
- Created and pushed the first commit (`63c54cd`).

**Challenges**: Git showed the error `Author identity unknown` when I tried to commit.

**Solution**: I set my Git name and university email, then committed and pushed the change again.

**Time spent**: 31 minutes .

---

###  Entry 2 - November 24, 2026, between 3:34 and 3:46 PM
**What I did**: Ran the starter code and checked the output.

**Details**:
- Ran the program in NetBeans with 18 processes, 2 CPUs and a 5000 ms time quantum.
- Both CPUs picked P1 and CPU-2 threw `IllegalThreadStateException`.
- Saved the original output to compare it with the final version.

**Challenges**: The same thread was picked twice, and some characters in the output appeared as question marks.

**Solution**: I identified the problem in `ReadyQueue.poll()` and kept the original output for the technical questions.

**Time spent**: 12 minutes .

---

### Entry 3 - November 24, 2026, completed by 3:46 PM
**What I did**: Added the ready queue lock (Feature 1).

**Details**:
- Imported `ReentrantLock` and added `queueLock` to the `ReadyQueue` class.
- Protected `add()`, `poll()`, `processOf()` and `snapshot()`.
- Used `try/finally` to release the lock safely.
- Ran the program and executed the commit and push commands.

**Challenges**: Both CPUs could access the shared list and map at the same time.

**Solution**: I used the same lock for all queue operations and kept `RaceWindow.pause()` in the original code.

**Time spent**: 12 minuets.

---

### Entry 4 -  November 24, 2026, approximately 3:46–3:54 PM
**What I did**: Protected the shared statistics (Feature 2).

**Details**:
- Added `statsLock` to the `SharedStats` class.
- Protected the three counters and their getter methods.
- Ran the program and checked the verification block.
- The only reported mismatch was the busy-waiting check.

**Challenges**: Updating the same counter from two threads could cause a lost update.

**Solution**: I used one statistics lock and released it with `finally` in all six methods.

**Time spent**: 8 min.

---

### Entry 5 -  November 24, 2026, approximately 3:54–4:06 PM
**What I did**: Added the counting semaphore (Feature 3) and tested the program.

**Details**:
- Added `readyCount` with an initial value of zero.
- Used `release()` when adding a process and `acquire()` before polling the queue.
- Added a shutdown signal for the waiting CPUs.
- The saved final output showed `All shared values are consistent` and `BUILD SUCCESSFUL`.
- Additional tests and the final push were reported completed.

**Challenges**: A CPU could stay blocked after the last process finished.

**Solution**: I added a completion check and released permits to wake the waiting CPUs.

**Time spent**: 12 min.

---

### Entry 6 - November 25, 2026, 5:41 PM - 6;33

**What I did**: Final testing and video demonstration.

**Details**: Fixed the output encoding in NetBeans,
reviewed the synchronization features, tested the program,
recorded the demonstration video, and uploaded it to Google Drive.

**Challenges**: The output contained question marks,
and the video exceeded three minutes.

**Solution**: Configured UTF-8 encoding, checked the
verification results, and trimmed the video to meet
the required duration.

**Time spent**: [52 min]
---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: 3 hours and 24 minutes (sum of the five supplied estimates; confirm against actual work).

**Most challenging part**: Making sure that all CPUs stop after the last process finishes.

**Most interesting learning**: How two CPUs can pick the same process when the ready queue is not protected.

**What I would do differently next time**: Start earlier, save the output after each feature, and check the console encoding before testing.

---

# Part B: Reflection (0.5 mark)

> Suggested drafts for review and rewriting in your own words. Confirm that the statements describe your actual understanding and experience.

> 🛑 **STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulationSync.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

## Question 1: What did you learn about synchronization?

> 💡 **TIP:** Talk about race conditions (read-modify-write), critical sections, mutual exclusion with `ReentrantLock` and `try/finally`, the role of a counting semaphore, and what surprised you when the starter failed.

**Your Answer:** *(5-7 sentences)*

I learned why synchronization is important when multiple threads use shared data. In my first run, both CPUs picked P1 and CPU-2 showed an error. I learned that updating a shared counter can also cause a race condition. I used `ReentrantLock` to protect the ready queue and the statistics. I used `finally` to make sure the lock is always released. I also learned how a semaphore can make a CPU wait for work without busy waiting.

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

The most challenging part was making the semaphore stop correctly. When the queue is empty, a CPU waits in `acquire()`. If the other CPU finishes the last process, no more processes will be added. This means the waiting CPU could remain blocked. I used a shutdown signal and checked the completed process count again after `acquire()`. This allows the CPUs to stop when all the work is finished.

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

I worked on one feature at a time instead of changing everything together. First, I ran the starter code and saved its output. Then I added the queue lock, the statistics lock and the semaphore in order. I also fixed the Git error by setting my name and university email. I checked the verification block after making changes. In the final run, the program reported that all shared values were consistent.

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

Synchronization can be used in many real applications. In a booking system, it can prevent two users from booking the same seat. In a banking system, a lock can protect a shared balance during updates. A website can use a lock to protect a shared counter from lost updates. A print queue can use a semaphore to wait until a print job is available. These examples are similar to the shared resources in my scheduler program.

### Optional: What would you like to learn more about?

Suggested answer: I would like to learn more about deadlocks and how operating systems prevent them.

### Optional: How confident do you feel about synchronization concepts now?

Suggested answer: Intermediate. I understand the basic use of locks and semaphores, but I need more practice with concurrent programs.

### Optional: Feedback on the assignment

Suggested answer: The verification block was helpful because it showed which part still needed to be fixed. Clearer console encoding instructions would also help.

---

# Part C: Technical Answers (0.5 mark)

> 🛑 **STOP:** You cannot answer these questions without understanding the code. Re-read `SchedulerSimulationSync.java` and **run it** first. Your answers must reference **your own code and your own output** (your student ID makes your output and your expected values unique).
>
> ⚠️ **WARNING:** Each answer must be **3 to 5 sentences**, with specific examples from your code or output. Use correct terms: race condition, critical section, mutual exclusion, mutex lock, semaphore, busy waiting, deadlock, producer, consumer.
>
> 💡 **TIP:** Keep the output of the **original starter** and the output of your **final version** in text files or screenshots, so you can copy real snippets for Question 1.

## Question 1: Race Condition in Your Own Output

**Question**: Run the **original starter** (before any fix) and paste the **verification block** of that run. Which value was wrong (expected vs observed)? Explain **step by step**, with two named threads/CPUs, how **one lost update** happens on one of the shared variables (read, `RaceWindow.pause()`, write). Why can the same bug happen on a real machine even without `RaceWindow`, and why is it hard to detect?

> ⚠️ **WARNING:** The snippet must come from **your own run** (with your student ID), not from a classmate or from this README.
>
> 💡 **TIP:** Use a small timeline: *CPU-1 reads `contextSwitchCount` = 12 → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13 → one increment is lost.* If your starter run crashed before printing numbers, run it several times (or paste the exception and the watchdog message and explain it).

**Your Answer:** *(3-5 sentences)*

In my original run, CPU-1 and CPU-2 both picked P1, causing `IllegalThreadStateException` in CPU-2 because a Java thread cannot be started twice. Although the starter printed `All shared values are consistent`, that does not prove the queue was safe, and no numerical counter mismatch can be identified from the displayed output. A possible lost-update example is that the process threads associated with CPU-1 and CPU-2 both read the same `contextSwitchCount` value, pause, and write the same incremented value. The operating system can interrupt or interleave these operations on a real machine even without `RaceWindow.pause()`. Such failures are difficult to detect because they depend on thread timing and may not occur on every run.

Verification block of the **original starter**:
```
Exception in thread "CPU-2" java.lang.IllegalThreadStateException
	at java.base/java.lang.Thread.start(Thread.java:1389)
	at CpuWorker.run(SchedulerSimulationSync.java:283)

??? VERIFICATION (expected values are computed from YOUR seed) ???
  Context switches (quanta executed)     expected ??       observed ??       ?
  Completed processes                    expected ??       observed ??       ?
  Total service time (ms)                expected ??????   observed ??????   ?
  Busy-waiting polls (must be 0)         expected ?        observed ?        ?
  ? All shared values are consistent.
```

Verification block of **my final version**:
```
??? VERIFICATION (expected values are computed from YOUR seed) ???
  Context switches (quanta executed)     expected ??       observed ??       ?
  Completed processes                    expected ??       observed ??       ?
  Total service time (ms)                expected ??????   observed ??????   ?
  Busy-waiting polls (must be 0)         expected ?        observed ?        ?
  ? All shared values are consistent.
```

The pasted blocks above are the actual saved output. The IDE displayed several digits and symbols as `?`. From the 18 burst times and the 5000 ms quantum, the expected values are 37 context switches, 18 completed processes, 127733 ms total service time, and 0 busy-waiting polls. The final success message confirms all four checks passed in that run. The numbers below are calculated from the burst times and inferred to match in the final run from its success message, not copied from a readable console. The original exception is the observed queue failure.

| Final check | Expected | Inferred observed |
|---|---:|---:|
| Context switches | 37 | 37 |
| Completed processes | 18 | 18 |
| Total service time (ms) | 127733 | 127733 |
| Busy-waiting polls | 0 | 0 |

**Explanation of the timeline:**
Illustrative example (not a measured counter trace): CPU-1’s process thread reads 12 → CPU-2’s process thread reads 12 → both pass through `RaceWindow.pause()` → CPU-1 writes 13 → CPU-2 writes 13. The result is 13 instead of 14, so one increment is lost.

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

I protected the ready queue list and map with `queueLock` and the three statistics counters with `statsLock`, including their getters. I used one statistics lock because it is simpler to manage, although independent counter operations may have to wait for one another. A separate queue lock allows queue operations and statistics operations to proceed independently. The locks provide mutual exclusion, and short critical sections with `finally` release support progress. The default `ReentrantLock` is not fair, so it does not guarantee bounded waiting or FIFO acquisition and starvation is theoretically possible.

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| `ReadyQueue.add()` | `queueLock` | Protects insertion into the list and map. |
| `ReadyQueue.poll()` | `queueLock` | Makes selecting and removing a thread atomic. |
| `ReadyQueue.processOf()` | `queueLock` | Protects the shared map lookup. |
| `ReadyQueue.snapshot()` | `queueLock` | Prevents concurrent modification during iteration. |
| `contextSwitchCount`: `incrementContextSwitch()`, `getContextSwitchCount()` | `statsLock` | Prevents lost increments and protects reads. |
| `completedProcessCount`: `incrementCompletedProcess()`, `getCompletedProcessCount()` | `statsLock` | Protects the completion count and its reads. |
| `totalServiceTime`: `addServiceTime()`, `getTotalServiceTime()` | `statsLock` | Protects accumulated service time and its reads. |

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

The starter polls the empty queue and sleeps for 20 ms before trying again, which causes unnecessary wakeups; the original run reported all checks consistent, implying zero busy-waiting polls in that particular run, although its numeric field was unreadable. After Feature 2, the saved output explicitly reported a busy-waiting mismatch, while the final run passed that check. The semaphore `readyCount` starts at zero because the queue is empty, and after the 18 initial `add()` calls it has 18 permits representing available processes before the CPUs start. Each CPU acquires a permit before polling and each insertion releases a permit. At completion, `release(SharedStats.totalCPUs)` wakes blocked CPUs so they can check the completed count and exit rather than wait forever.

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*

**Classical problem and roles**:
The classical problem is the producer-consumer problem; the main thread initially produces processes, and CPU workers consume them and also produce new queue entries when unfinished processes are re-enqueued.

**Semaphores for a bounded queue (name and initial value)**:
For a bounded queue of capacity K, use `empty = K`, `full = 0`, and `mutex = 1`.

**Deadlock scenario and prevention**:
If a producer holds the mutex while waiting for an empty slot in a full queue, a consumer cannot acquire the mutex to remove a process. To prevent this deadlock, wait for `empty` or `full` before acquiring the mutex; this breaks the circular-wait dependency in this scenario.

## Summary

**Key concepts I understood through these questions:**
1. Race conditions and critical sections.
2. Mutex locks and mutual exclusion.
3. Counting semaphores and clean shutdown.

**Concepts I need to study more:**
1. Fair locking and starvation.
2. Bounded-buffer synchronization and deadlock prevention.

---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [x] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [x] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [x] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [x] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [x] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [x] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [x] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [x] **The four verification lines are ✔ in 5 consecutive runs**
- [x] Every lock is released in a `finally` block
- [x] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [x] Each feature has clear comments

**Commits**
- [x] **At least 4 meaningful commits, ideally 7 or more**
- [x] **One commit per feature**
- [x] Commits are spread over **different dates** (not all in the last hour)
- [x] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [x] Full name and student ID filled in at the top
- [x] Development log has **5+ entries** on different dates
- [x] Reflection: 4 questions, 5-7 sentences each
- [x] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [x] No `[...]` placeholders left
- [x] No section headers deleted

**Video**
- [x] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [x] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [x] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [x] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
