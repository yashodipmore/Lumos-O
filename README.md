# Lumos O - Mini OS (Linux-based)

Lumos O is a lightweight, Linux-based mini operating system designed for educational and experimental purposes. It provides fundamental OS functionalities, including process management, file system support, and minimal driver implementations. Lumos O serves as an excellent learning tool for understanding low-level system programming and operating system design.

## Tech Stack
Lumos O is built using a combination of programming languages, development tools, and virtualization platforms:
- **Kernel**: Custom-built Linux kernel with minimal modifications
- **Programming Languages**: C (system programming), Assembly (low-level hardware interactions)
- **Build System**: GCC (GNU Compiler Collection), Make (build automation tool)
- **Filesystem**: Custom RAM-based minimal filesystem (supports basic file operations)
- **Shell Scripting**: Bash scripts for automated installation, build, and execution
- **Virtualization**: QEMU is used for testing the OS in a virtual environment
- **Drivers**: Basic drivers for character devices and file system support

## Features
Lumos O includes various features that provide basic OS functionality:
- **Custom Kernel**: A minimalistic kernel supporting basic process management and memory allocation
- **Process Management**: Allows running multiple processes, listing active processes, and terminating them
- **Filesystem Support**: RAM-based file system with commands like `ls`, `cat`, and `echo`
- **Minimal Shell**: A command-line interface for interacting with the OS
- **Device Drivers**: Basic character device drivers for handling input/output operations
- **Virtualization Support**: Can be executed using QEMU for testing without real hardware

## Installation & Setup
### Prerequisites
To build and run Lumos O, ensure you have the following dependencies installed:
- **GCC** (GNU Compiler Collection)
- **QEMU** (for virtualization and testing)
- **Make** (build automation tool)
- **Bash Shell** (for executing installation and build scripts)

### Building and Running Lumos O
To set up Lumos O on your system, follow these steps:
```sh
# Grant execution permissions to scripts
chmod +x build.sh install.sh run.sh

# Build the kernel and system components
./build.sh

# Install necessary components
./install.sh

# Boot Lumos O in QEMU
./run.sh
```

## Usage & Commands
Once Lumos O is running, you can interact with the system using its built-in shell. Below are some basic commands available:
```sh
ls            # List files in the current directory
cat <file>    # Display the contents of a file
echo "text" > <file>  # Write text to a file
ps            # Display a list of running processes
kill <PID>    # Terminate a process with the given Process ID (PID)
clear         # Clear the terminal screen
help          # Display a list of available commands
shutdown      # Power off the OS
```

### Example Usage
```sh
> ls
bin  dev  home  usr
> echo "Hello, Lumos O!" > welcome.txt
> cat welcome.txt
Hello, Lumos O!
> ps
PID   COMMAND
1     init
2     shell
> kill 2
Process 2 terminated.
```

## Expected Output
After executing `./run.sh`, you should see the following output:
```
Lumos O Booting...
Initializing Kernel...
Mounting Filesystem...
Loading Drivers...
Starting Shell...
Welcome to Lumos Shell
> _
```

## System Architecture
Lumos O follows a structured modular architecture:
1. **Boot Process**: The system initializes the kernel, loads drivers, and mounts the filesystem.
2. **Kernel**: Manages processes, memory, and low-level hardware communication.
3. **Shell**: Provides an interface for users to execute commands and manage the system.
4. **Filesystem**: A RAM-based filesystem that supports basic file operations.
5. **Drivers**: Custom device drivers for handling character devices and file system interactions.

## Debugging and Logs
To debug any issues while running Lumos O, check the log files generated in the system:
```sh
cat /var/log/lumos.log  # View system logs
```
If QEMU fails to boot, run the following command for detailed debugging:
```sh
qemu-system-x86_64 -kernel lumos-kernel -d int,cpu_reset
```

## Contribution Guidelines
Contributions are welcome! Follow these steps to contribute:
1. **Fork the Repository**: Create a copy of the project in your GitHub account.
2. **Create a Feature Branch**: Develop your changes in a separate branch.
3. **Write Clean Code**: Follow best coding practices and document your code.
4. **Submit a Pull Request**: Request to merge your changes into the main repository.

## Future Enhancements
- Implement a basic GUI for improved user interaction.
- Add networking support for remote access.
- Improve filesystem efficiency with persistent storage.
- Enhance process scheduling algorithms for better performance.

---
Developed with ❤️ by the Lumos O Team.

