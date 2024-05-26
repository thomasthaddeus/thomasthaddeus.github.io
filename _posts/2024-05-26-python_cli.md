---
layout: post
title: "Python CLI on Windows"
author: "Thaddeus Thomas"
date: 2024-05-26
categories: python cli
---

## Overview

This documentation covers various methods to set up Python and Python programs to run directly from the command line on a Windows system.

---

### 1. Setting Up Python Itself

#### Step 1: Install Python
1. **Download Python:**
   - Download the latest Python installer from [python.org](https://www.python.org/).
2. **Run the Installer:**
   - Run the installer and ensure you check the option "Add Python to PATH" before clicking "Install Now".

#### Step 2: Verify Python Installation
- Open Command Prompt and type:

  ```cmd
  python --version
  ```
  This should display the installed version of Python.

---

### 2. Adding Python Programs to PATH

#### Method 1: Directly Adding Python Scripts Directory to PATH

1. **Locate Your Script Directory:**
   - Find the directory where your Python scripts are located (e.g., `C:\MyPythonScripts`).

2. **Add Directory to PATH:**
   - Press `Win + X`, select `System`.
   - Click on `Advanced system settings`.
   - Click `Environment Variables`.
   - Under `System variables`, select `Path`, and click `Edit`.
   - Click `New` and add the path to your Python scripts directory.
   - Click `OK` to apply the changes.

3. **Run the Script from Command Line:**
   - Open a new Command Prompt window and type the script name:

    ```cmd
     my_script.py
     ```

   - If you prefer not to type `python` before the script, rename your script to remove the `.py` extension:
     ```cmd
     my_script
     ```

#### Method 2: Using Shebang Line in Scripts

1. **Add Shebang Line:**
   - Open your Python script in a text editor.
   - Add the following line at the top:
     
     ```python
     #! python
     ```

2. **Make the Script Executable:**
   - Rename the script to remove the `.py` extension if desired.
   - Add the script directory to PATH as described above.

3. **Run the Script:**
   - Open Command Prompt and type the script name.

#### Method 3: Creating Batch Files

1. **Create a Batch File:**
   - Open Notepad and write the following line:
     ```batch
     @echo off
     python C:\MyPythonScripts\my_script.py %*
     ```
   - Save the file with a `.bat` extension (e.g., `my_script.bat`).

2. **Add Batch File Directory to PATH:**
   - Follow the steps to add the directory containing the batch file to PATH.

3. **Run the Batch File:**
   - Open Command Prompt and type the batch file name:
     ```cmd
     my_script
     ```

#### Method 4: Setting File Associations (Optional)

1. **Associate `.py` Files with Python:**
   - Open Command Prompt as Administrator.
   - Run the following commands:
     ```cmd
     assoc .py=Python.File
     ftype Python.File="C:\Path\To\Python\python.exe" "%1" %*
     ```
   - Replace `C:\Path\To\Python\python.exe` with the path to your Python executable.

2. **Run the Script Directly:**
   - Open Command Prompt and type the script name with or without `.py` extension based on your preference:
     ```cmd
     my_script.py
     ```

---

### Summary

By following these steps, you can set up Python and your Python programs to run from the command line in various ways. Whether you choose to add directories to PATH, use shebang lines, create batch files, or set file associations, these methods allow you to execute Python scripts conveniently from the command line on Windows.
