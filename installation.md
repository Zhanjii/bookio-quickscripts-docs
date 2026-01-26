---
layout: default
title: Installation
nav_order: 3
description: "Setup and installation instructions"
---

# Installation Guide

## Prerequisites

### System Requirements
- **Operating System**: Windows 10/11, macOS 10.15+, or Linux (Ubuntu 20.04+)
- **Python**: 3.8 or higher
- **Memory**: Minimum 4GB RAM (8GB recommended)
- **Storage**: At least 500MB for application and dependencies

### Required Software
- Python 3.8+ with pip
- Git (for cloning repository)
- Visual C++ Build Tools (Windows only, for some dependencies)

## Installation Steps

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/book-io-quickscripts.git
cd book-io-quickscripts
```

### 2. Create Virtual Environment (Recommended)
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Verify Installation
```bash
python -m book_io_quickscripts.main
```

## Building Executable

### Using PyInstaller

1. **Install PyInstaller**
   ```bash
   pip install pyinstaller
   ```

2. **Build the Executable**
   ```bash
   # Windows
   pyinstaller --name "Book.io QuickScripts" ^
               --windowed ^
               --icon=icon/book.io.ico ^
               --add-data "icon;icon" ^
               --add-data "examples;examples" ^
               --hidden-import customtkinter ^
               --hidden-import PIL._tkinter_finder ^
               --collect-data customtkinter ^
               src/book_io_quickscripts/main.py

   # macOS/Linux
   pyinstaller --name "Book.io QuickScripts" \
               --windowed \
               --icon=icon/book.io.ico \
               --add-data "icon:icon" \
               --add-data "examples:examples" \
               --hidden-import customtkinter \
               --hidden-import PIL._tkinter_finder \
               --collect-data customtkinter \
               src/book_io_quickscripts/main.py
   ```

3. **Locate the Executable**
   - Windows: `dist/Book.io QuickScripts/Book.io QuickScripts.exe`
   - macOS: `dist/Book.io QuickScripts/Book.io QuickScripts.app`
   - Linux: `dist/Book.io QuickScripts/Book.io QuickScripts`

### Alternative: Using cx_Freeze

1. **Install cx_Freeze**
   ```bash
   pip install cx_freeze
   ```

2. **Create setup.py**
   ```python
   from cx_Freeze import setup, Executable
   import sys

   build_exe_options = {
       "packages": ["customtkinter", "PIL", "tkinter"],
       "include_files": ["icon/", "examples/"]
   }

   base = None
   if sys.platform == "win32":
       base = "Win32GUI"

   setup(
       name="Book.io QuickScripts",
       version="1.0.0",
       description="Book.io workflow automation tools",
       options={"build_exe": build_exe_options},
       executables=[Executable("src/book_io_quickscripts/main.py", base=base)]
   )
   ```

3. **Build**
   ```bash
   python setup.py build
   ```

## Troubleshooting Installation

### Common Issues

#### 1. ModuleNotFoundError: No module named 'customtkinter'
**Solution**: Ensure all dependencies are installed:
```bash
pip install --upgrade customtkinter
```

#### 2. ImportError: cannot import name 'ImageTk' from 'PIL'
**Solution**: Install or reinstall Pillow:
```bash
pip uninstall Pillow
pip install Pillow
```

#### 3. Permission Denied on Windows
**Solution**: Run command prompt as Administrator or use:
```bash
pip install --user -r requirements.txt
```

#### 4. Build Tools Error on Windows
**Solution**: Install Visual C++ Build Tools:
- Download from [Microsoft Build Tools](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2022)
- Install "Desktop development with C++" workload

#### 5. Icon Not Found When Running Executable
**Solution**: Ensure icon path is included in build:
- Check `--add-data` parameter includes icon folder
- Verify icon file exists at `icon/book.io.ico`

### Platform-Specific Notes

#### Windows
- May require running as Administrator for certain operations
- Windows Defender might flag new executables - add exception if needed

#### macOS
- May need to allow app in System Preferences > Security & Privacy
- For M1/M2 Macs, ensure using ARM64 compatible Python

#### Linux
- May need to install additional system packages:
  ```bash
  sudo apt-get install python3-tk python3-pil python3-pil.imagetk
  ```

## Development Installation

For contributing to the project:

1. **Fork and Clone**
   ```bash
   git clone https://github.com/yourusername/book-io-quickscripts.git
   cd book-io-quickscripts
   ```

2. **Install in Development Mode**
   ```bash
   pip install -e .
   ```

3. **Install Development Dependencies**
   ```bash
   pip install -r requirements-dev.txt
   ```

4. **Run Tests**
   ```bash
   pytest tests/
   ```

## Updating

To update to the latest version:

1. **From Git**
   ```bash
   git pull origin main
   pip install -r requirements.txt
   ```

2. **Executable Users**
   - Download latest release from GitHub
   - Replace old executable with new version
   - Configuration files will be preserved