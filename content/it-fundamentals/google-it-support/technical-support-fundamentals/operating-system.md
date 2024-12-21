---
LastModifierDisplayName: AbuTurab
LastModifierEmail: cyberfrontofficial@proton.me
title: Operating Systems
date: 2022-06-01 11:00:00 +0500
weight: 3
collapsibleMenu: true
alwaysOpen: false
---

## **What is an OS?**

An operating system (OS) is software that manages computer hardware and facilitates communication between applications and the underlying hardware. It oversees processes, allocating resources like CPU and memory, and provides a file system for data organization. The OS interacts with input/output devices and often includes a user interface for human-computer interaction. It ensures security through features like user authentication and access control. Examples include Windows, macOS, Linux, and mobile OS like Android and iOS. The OS is a fundamental component that enables the proper functioning of computers and devices.

## **Remote Connection and SSH**

### Remote Connection
  
  Allows us to manage multiple machines from anywhere in the world.

### Secure Shell (SSH)
  
  A protocol implemented by other programs to securely access one computer from another.
- Popular software to work with SSH, on Linux, OpenSSH program, while on Windows, PuTTY is used.
- In SSH, a pair of public and private keys is used to authenticate the process.
- To securely connect to a remote machine, a VPN is used.

### VPN
  
  Allows you to connect to a private network, like your work network, over the Internet.

## **Remote Connections on Windows**

### PuTTY
  
  A free, open source software that you can use to make remote connections through several network protocols, including SSH.
- DOING PuTTY can be used from CL, as `putty.exe & ssh user@ip\<address>`

- PuTTY comes with a Plink or PuTTYlink program, which can also be used for SSH-ing to other computers.
- Microsoft provides another way to remotely connect with Windows computer via GUI, called Remote Desktop Protocol (RDP).

## **Components of an Operating System**

### Operating System
  
  The whole package that manages our computer’s resources and lets us interact with it.
- Two main parts
- 1) Kernel: Storage and file management, processes, memory control, I/O management
- 2) User Space: Everything out of the scope of the Kernel, like application, CLI tools etc

## **Files and File Systems**
  
  File storage include three things:
  
  1) Data 
  2) File handling 
  3) Metadata

### Block Storage
  
  Improves faster handling of data because the data is not stored as one long piece and can be accessed quicker.

## **Process Management**

### Process
  
  A program that is executing, like our internet browser or text editor.

### Program
  
  An application that we can run, like Chrome.

### Time slice
  
  A very short interval of time, that gets allocated to a process for CPU execution.

### Role of Kernel

- Create processes
- efficiently schedules them
- Manages how processes are terminated

## **Memory Management**

### Virtual Memory
  
  The combination of hard drive space and RAM that acts like memory that our processes can use.

### Swap Space
  
  Allocated Space for virtual memory.

## **I/O Management**

- Kernel does Input/Output devices by managing their intercommunicating and resource management etc.

## **Interacting with the OS: User Space**
  
  Two ways to interact with the OS
- Shell
    
    A program that interprets text commands and sends them to the OS to execute.
- GUI

## **Logs**
  
  Files that record system events on our computer, just like a system's diary.

## **The Boot Process**
  
  The computer boots in the following order.

### BIOS/UEFI
  
  A low-level software that initializes our computer's hardware to make sure everything is good to go.

### POST
  
  Power on Self Test (POST) is performed to make sure the computer is in proper working order.

### Bootloader
  
  A small program that loads the OS.

### Kernel
- System Processes
- User Space
