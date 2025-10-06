# Introduction
## How to use this
- Read through the different subheadings. 
- Note that the links are all collated in references.md and can be referenced later
- Set up your Mac (see later)
  
## The Shell
Before the mouse and the graphical user interface, there was the shell, a computer program that controls your computer through a text-based interface.  

### Terminal in MacOS
In the Mac, the shell is accessed using the Terminal. 
Find the Terminal in Application/Utilities, then drag to the Dock.

Learn more about the Terminal **later** from Apple's [Terminal User Guide](https://support.apple.com/guide/terminal/welcome/mac0)

### Shell in Windows
In Windows, there are two command-line shells:
- Command shell (accessed via Start Menu Search "cmd" or "command prompt")
- PowerShell. 

Learn more **later** about [Windows Commands](https://learn.microsoft.com/en-us/windows-server/administration/windows-commands/windows-commands)

## Mac OS Environments : zsh and bash

There are many shell choices.  Mac used to come default with **bash** but now comes default with **zsh**.  This may be important if you use multiple OSes.  You would want to know what shell(s) you are using so that shell scripts work across different OSes.  zsh was built based on bash, has command line completion and is extensible with plug-ins. 

When working with shell code, some commands or syntax may differ between zsh and bash.  
[Geeks for Geeks discusses zsh and bash](https://www.geeksforgeeks.org/linux-unix/bash-scripting-difference-between-zsh-and-bash/}).  You can proceed without reading that for now.

### Basic Commands 

## Important Basic File Management Commands

Here is a table of important file management commands, including the Windows shell equivalent for comparison:

| Command | Action | Example | Explanation | Windows CMD Equivalent |
| :--- | :--- | :--- | :--- | :--- |
| **`pwd`** | **P**rint **W**orking **D**irectory | `pwd` | Shows the full path to your current location (e.g., `/Users/username/`). | `cd` |
| **`ls`** | **L**i**s**t files and folders | `ls -lha` | Shows the contents of the current directory. | `dir` |
| **`cd`** | **C**hange **D**irectory | `cd Documents`<br>`cd ..` | Moves into the specified folder or up one level (`..`). | `cd <path>`<br>`cd ..` |
| **`mkdir`** | **M**a**k**e **Dir**ectory | `mkdir Reports` | Creates a new folder (directory). | `mkdir <name>` |
| **`touch`** | Create empty file  | `touch newfile.txt` | Creates an empty file or updates a timestamp | `type nul > newfile.txt` |
| **`cp`** | **C**o**p**y files or folders | `cp file1.txt folderA/`<br>`cp -r folderA folderB/` | Copies a file or a folder (using `-r` for recursive). | `copy <src> <dest>` |
| **`mv`** | **M**o**v**e or Rename files/folders | `mv oldname.txt newname.txt`<br>`mv file.txt /tmp` | Moves a file to a new location or renames it. | `move <src> <dest>`<br>`ren <old> <new>` |
| **`rm`** | **R**e**m**ove files | `rm badfile.txt` | **Permanently deletes** the file. Use with caution\! | `del <file>` |
| **`rm -r`**| **R**e**m**ove folders **R**ecursively | `rm -r old_folder` | **Permanently deletes** the folder and all of its contents. | `rmdir /s <folder>` |
| **`cat`** | **Cat**enate (View file contents) | `cat log.txt` | Prints the entire content of a file to the terminal. | `type <file>` |
| **`nano`**| Basic text editor | `nano script.sh` | Opens the file in the `nano` editor to modify its contents. | `notepad <file>` |

## MacOS Paths

In MacOS and Linux, the file structure is a single unified tree.  There is one root.  In Windows, there are multiple root directories.

In the Mac GUI, "Macintosh HD" is the root In the command line it is represented by `/`.  In the Terminal, to go to the root folder, you can type `cd /`.  

This is the absolute path to your home folder `/Users/username`.  
This is the shortcut  `~`.  
This is the absolute path to a folder1 within Documents `Users/username/Documents/folder1`
This is the relative path if you are at your home folder `~/Documents/folder1`
This refers to the current directory `.`.  
This refers to the parent directory `..`.  
Thus if you `cd ~/Documents/folder1`, you can go to folder2 (a sibling of folder1) from there by `cd ../folder2`.  

## Source Code Editors and Integrated Development Environments (IDEs)

Source code editors are text editor programs.  It can be a stand-alone application (eg, nano, vim) or it can be built into an integrated evelopment environment (IDE). An IDE allows you to edit the files, use the Terminal within the IDE and see your files using a panel all within the same window. 

IDEs can complete code, highlight the syntax, show differences between files, run code, and many more.  Its function can be enhanced by extensions which can be installed.

Examples of IDEs are Visual Studio Code, VSCodium, Cursor


# Setup
## Prerequisites
- [Download Visual Studio Code](https://code.visualstudio.com/docs/setup/mac)
- [Create a github account](https://github.com/signup?ref_cta=Sign+up&ref_loc=header+logged+out&ref_page=%2F&source=header-home) with your primary personal or work email.
- Download github mobile on your phone. (you will need this)

## Homebrew
- Homebrew is a package manager for installing applications with and without a GUI.
- To install homebrew, copy and paste this in the Terminal
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
``` 
- verify installation with `brew --version`
## gh
- `gh` is the [Github Command Line Interface](https://cli.github.com/)
- To install `gh`, paste this in Terminal
```
brew install gh
```
- verify installation with `gh version` 
## rclone
- [Rclone](https://rclone.org/) helps you manage files in cloud storage devices
- To install rclone, paste this in Terminal
``` 
sudo -v ; curl https://rclone.org/install.sh | sudo bash
```
- verify installation with `rclone version` 
- it is possible to `brew install rclone` but this is known to exclude `rclone mount` which is a command needed to install volumes.  So do not install via brew.  

## Authenticate github for Terminal
- To use github, you need to authenticate your github account to work on the command line  through a series of interactive prompts in Terminal.  After typing the command below, you will be asked several questions.  Reply as indicated.  
```
gh auth login
```
  - For Account Type , choose **Github.com**
  - For Protocol, choose **HTTPS**
  - Authenticate Git with your GitHub credentials? **Yes**
  - For Authentication Method, choose **Login with a web browser**
  - This should give you a one time code which you will be prompted to copy.  Press Enter to open a browser directly to github.  You would need to enter your one-time code (paste it). 
  - To confirm authentication 
```
  gh auth status
```
  
## Configure rclone
- To follow

# Art Related Programs
## For Media and Scripting via brew
| Program | Homebrew Command | Rationale |
| :--- | :--- | :--- |
| **Python** (for scripting) | `brew install python` | Essential for automating tasks in Blender, Maya, or custom pipelines. |
| **FFmpeg** (Video/Audio) | `brew install ffmpeg` | The industry-standard command-line tool for video and audio conversion, scaling, and manipulation. |
| **ImageMagick** (Image Utility) | `brew install imagemagick` | Batch process and manipulate image assets (e.g., resizing textures) quickly from the command line. |
| **git** (Version Control) | `brew install git` | Although macOS has a version of Git, installing via Homebrew ensures you have the latest version. |

## Graphics Software and CLI 

| Program | CLI Status |
| :--- | :--- |
| **Blender** | It can be run in **batch mode** (headless) via the command line for tasks like rendering, format conversions, and scene export. |
| **Maya** | While primarily a GUI application, it can be run in **batch mode** (headless) via the command line for tasks like rendering, scene conversions, and script execution. |
| **Nuke** | Has a very powerful command-line mode for batch rendering, script execution, and heavy pipeline automation. |
| **V-Ray** | The V-Ray Standalone renderer is a command-line application designed for farm rendering and batch processing without needing the host 3D application (like Maya or 3ds Max) installed. |
| **Substance Designer** | Primarily GUI; batch processing is done through a separate command-line tool called **Substance Automation Toolkit (SAT)**. |
| **Substance Painter** | Primarily GUI; batch processing and exporting are done through the **Substance Automation Toolkit (SAT)**. |
| **Unreal Engine** | Has command-line arguments (for launching, compiling, and running automation tests), but no true CLI for scene manipulation. |
| **Photoshop** | Primarily GUI; heavy automation relies on its built-in scripting (ExtendScript) or Actions, not a traditional CLI. |
| **Marmoset Toolbag** | Primarily GUI; does not feature a dedicated CLI. |
| **Marvelous Designer** | Primarily GUI; does feature a dedicated CLI. |
| **ZBrush** | Primarily GUI; relies on custom macros and ZScript for limited automation, not a command-line interface. |
| **Mudbox** | Primarily GUI; does not feature a dedicated CLI. |
| **UVLayout** | Primarily GUI; can be launched with command-line options, but operation is interactive. |
| **Mari** | Primarily GUI; does not feature a dedicated CLI for core painting operations. |
| **SpeedTree** | Primarily GUI; does not feature a dedicated CLI. |