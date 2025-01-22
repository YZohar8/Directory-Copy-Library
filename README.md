# Directory Copy Library 📂

## Overview 🎯
A professional C library implementation inspired by Python's `shutil.copytree`, providing robust directory tree copying functionality with advanced features for handling symbolic links and file permissions.

## Features ⭐
- **Complete Directory Tree Copying** 🌲
  - Recursively copies entire directory structures
  - Preserves file hierarchy and relationships
  - Handles nested subdirectories seamlessly

- **Advanced File Handling** 📄
  - Symbolic link support
  - Permission preservation
  - Error recovery mechanisms

- **Flexible Configuration** ⚙️
  - Customizable copying behavior
  - Command-line flag support
  - Extensive error reporting

## Technical Architecture 🏗️

### Core Components

#### 1. File Copy System 📋
```c
int copy_file(const char* source, const char* destination, 
              bool copy_symlinks, bool copy_permissions)
```
- Handles individual file copying
- Manages symbolic link processing
- Controls permission inheritance

#### 2. Directory Management 📁
```c
int create_directory(const char* path)
int copy_directory(const char* source, const char* destination, 
                  bool copy_symlinks, bool copy_permissions)
```
- Creates directory structures
- Manages recursive copying
- Handles parent directory creation

## Installation Guide 💾

### Prerequisites
- GCC Compiler
- Make utility
- POSIX-compliant system

### Building the Library 🛠️

1. **Compile the Library**
```bash
git clone https://github.com/YZohar8/Directory-Copy-Library.git
cd Directory-Copy-Library
gcc -c copytree.c -o copytree.o
ar rcs libcopytree.a copytree.o
```

2. **Build Main Program**
```bash
gcc part3.c -L. -lcopytree -o main_program
```

## Usage Guide 📚

### Basic Usage 🚀
Copy a directory with default settings:
```bash
./main_program source_directory destination_directory
```

### Advanced Options 🔧
```bash
# Copy with symbolic links
./main_program -l source_directory destination_directory

# Copy with permissions
./main_program -p source_directory destination_directory

# Copy with both options
./main_program -l -p source_directory destination_directory
```

### Directory Structure Examples 📋

#### Source Structure
```
source_directory/
├── documents/
│   ├── report.pdf
│   └── data.csv
├── images/
│   ├── photo1.jpg
│   └── photo2.jpg
└── config.link -> ../config.txt
```

#### Destination Result
```
destination_directory/
├── documents/
│   ├── report.pdf
│   └── data.csv
├── images/
│   ├── photo1.jpg
│   └── photo2.jpg
└── config.link -> ../config.txt
```

## Error Handling 🚨

### Common Error Scenarios
- Permission denied
- Path not found
- Symbolic link errors
- Disk space issues

### Error Output Format
```bash
perror("COMMAND failed: detailed error message")
```

## Testing Framework 🧪

### Running Tests
```bash
# Execute test suite
sudo python3 part3_tests.py

# View test results
cat test_output.txt
```

### Test Coverage
- File copying accuracy
- Directory structure preservation
- Symbolic link handling
- Permission management
- Error recovery
---
