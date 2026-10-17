# sysprog-tools

Learning the system programming tools by using them on real bugs: gdb, Valgrind, AddressSanitizer / UBSan / ThreadSanitizer,
strace, processes, threads, mutexes, races and deadlocks. Every program is typed, run, crashed and explained.

## Layout

One folder per day:

| Folder | Topic | Status |
|---|---|---|
| `day00-setup` | Compiler flags, exit codes of crashes (139, 134) | |
| `day01-bytes-pointers` | Bytes, pointers, endianness with gdb's `x` | |
| `day02-memory-map` | `/proc/PID/maps`: stack, heap, .data, .bss, .text, ASLR | |
| `day03-stack-frames` | Stack frames and return addresses in raw memory | |
| `day04-crashes` | NULL, stack overflow, core dumps, stack canary | |
| `day05-valgrind` | Ten memory bugs and every Valgrind error they produce | |
| `day06-leaks-watchpoints` | Leak types, watchpoints, Valgrind + gdb together | |
| `day07-sanitizers` | ASan, LSan, UBSan | |
| `day08-processes` | fork, copy-on-write, zombies, strace | |
| `day09-races` | A race at the assembly level, Helgrind, TSan | |
| `day10-mutexes-deadlock` | Mutexes, a live deadlock, attaching gdb | |
| `day11-capstone` | Four hidden bugs, one tool at a time | |

✅ done · 🟨 in progress

[`CHEATSHEET.md`](CHEATSHEET.md) collects the commands and messages worth remembering.

## Build

```sh
gcc -g -O0 -Wall -Wextra -o prog prog.c                 # for gdb and Valgrind
gcc -g -fsanitize=address,undefined -o prog prog.c      # sanitizers
```

Compiled programs (files with no extension), core dumps and Valgrind output are ignored by `.gitignore`.
