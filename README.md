# PennOS

## Externalized Repository

This repository has been modified to adhere to the academic integrity policy outlined in the CIS 3800 (Operating Systems) Syllabus. All `.h`, `.c`, and `Makefiles` have been removed from this repository. The live documentation for this project can be found at [PennOS](https://vedanshgoenka.github.io/PennOS-24sp-External/) and contains more detailed information about the implementation.

### Academic Integrity Compliance

The CIS 3800 syllabus states:

"You are not allowed to post your code from this course in a separate public repository or anywhere else that is publicly accessible. Doing so is against the academic conduct policy..."

### Project Overview

PennOS is our comprehensive operating system simulation project that demonstrates key concepts in OS design and implementation. We've included components such as process management, file system operations, and shell functionality.

The project highlights:

- Operating system architecture
- File system design and implementation
- Process scheduling and management
- Shell development and command execution

### Additional Information

For those interested in learning more about the technical details, implementation specifics, or seeing a demonstration of this project, please contact the authors directly using the email addresses provided in the Author Information section

## Author Information

| Author          | Email (.upenn.edu) |
|-----------------|---------------------|
| Michael Alfano  | malfano@seas       |
| Vedansh Goenka  | vedanshg@seas      |
| Arjun Arasappan | arjaras@seas       |
| Rohan Shah      | rohsha@sas         |

## Submitted Source Files - REMOVED

### Top Level

- src/logging.c
- src/logging.h
- src/pcb.h
- src/pennos.h
- src/sys_call.c
- src/sys_call.h

### PennFAT

For executing PennFAT:

- src/pennfat.c
- src/pennfat.h

General PennFAT files:

- src/pennfat/fs_utils.c
- src/pennfat/fs_utils.h
- src/pennfat/k_fd_structs.h
- src/pennfat/k_fs_structs.h
- src/pennfat/k_pennfat.c
- src/pennfat/k_pennfat.c
- src/pennfat/u_pennfat.h
- src/pennfat/s_pennfat.c
- src/pennfat/s_pennfat.h
- src/pennfat/u_pennfat.c
- src/pennfat/u_pennfat.h
- src/pennfat/u_test_suite.c
- src/pennfat/u_test_suite.h

For testing k level functions:

- src/test_routines.c
- src/test_routines.h

### Kernel

For executing the kernel:

- src/kernel.c
- src/kernel.h

General Kernel files:

- src/pennkernel/pcb_deque.c
- src/pennkernel/pcb_deque.h
- src/pennkernel/pid_deque.c
- src/pennkernel/pid_deque.h

### Shell

- src/shell/shell_func.c
- src/shell/shell_func.h
- src/shell/stress.c
- src/shell/stress.h

### Util

- src/util/spthread.c

## Compilation Instructions

Perform `make` at the top level in the code heirarchy to compile the code.

### Penn OS

To execute Penn OS enter the following at the top level after making:

`./bin/pennos`

### PennFAT

To execute PennFAT enter the following at the top level after making:

`./bin/pennfat`

### Overview of Work Accomplished

Over the course of this project we designed and implemented PennOS, a simulated os that can handle many aspects of OS functionality. This includes process management, file system interactions (PennFAT), and basic shell operations.

#### Key accomplishments

- **PennFAT Implementation**: Developed a fully functional file allocation table (FAT) based file system (PennFAT). PennFAT supports file creation, deletion, reading, and writing, along with permission handling, and other expected functionality of a file system.
- **Kernel Implementation**: Kernel capabilities to manage processes with PCB and PID management systems. This enables process scheduling and management.
- **Shell Functionality**: Built a shell that allows for process interaction, file system navigation, and testing with custom-built commands and scripts.
- **Testing Framework**: Developed testing suites for both k-level and u-level functions to make sure the OS components functioned properly.

This project gave us a solid foundation of operating systems.

### Description of Code and Code Layout

Our codebase is structured into several sections:

#### PennFAT

- **Files**: Includes files such as `pennfat.c` and `pennfat.h` which have the high level logic for enabline file system operations.
- **Utilities**: Includes files such as `fs_utils.c` and `fs_utils.h` for lower-level file system operations and helper functions.
- **Data Structures**: Includes files such as `k_fd_structs.h` and `k_fs_structs.h` which define the data models for file descriptors and file system metadata.
- **Testing Suite**: Includes files such as `u_test_suite.c` and `u_test_suite.h` which are used to test file system integrity and functionality.

#### PennKernel

- **Process Management**: Includes `pcb_deque.c` and `pcb_deque.h` which manage the deque operations for process control blocks used for process scheduling. Refer to `kernel.c` for integration details.
- **PID Management**: Includes `pid_deque.c` and `pid_deque.h` which are used for handling process identifiers aiding in process management. See `kernel.c` for usage examples.
- **Logging**: The `logging.c` file is utilized within the kernel for logging various system events and process states, enhancing debugging and system monitoring.

#### Shell

- **Core Functionality**: The files `shell_func.c` and `shell_func.h` provide the essential framework and functions for shell operations, enabling command parsing, execution, and signal handling.
- **Command Execution**: The shell supports a variety of built-in commands and the ability to execute custom scripts as detailed in `pennos.c`. It handles command execution with process management, including foreground and background execution.
- **Signal Handling**: Signal management for processes is implemented in `sys_call.c`, allowing the shell to send signals like SIGSTOP, SIGCONT, and SIGTERM to control processes.
- **Error Handling**: Robust error handling mechanisms are integrated within the shell to manage and log errors during command execution and file operations.

#### Utility

- **Threads**: The `spthread.c` file.

#### Source Top Level

- **System Integration**: Includes files like `sys_call.c` and `sys_call.h` for handling system calls, and `logging.c` and `logging.h` for system logging.
- **Errors**: Includes centralized custom error codes with error desciption and outputing functionality.

### General Comments

- **Documentation**: inline comments and module-level documentation are provided to help with clarity.
- **Contact**: if you have any questions please don't hesitate to email us.
