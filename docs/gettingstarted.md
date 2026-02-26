---
title: Getting Started
description: Getting started with the workshop outline and how to configure
  your enviornment.
icon: lucide/rocket
hide: 
    - navigation
---

<!-- Acronyms -->
*[CLI]: Command-Line Interface
*[stdin]: Standard Input
*[stdout]: Standard Output
*[stderr]: Standard Error
*[WSL]: Windows Subsystem for Linux
*[OS]: Operating System
*[LTS]: Long Term Support
*[BIOS]: Basic Input/Output System - PC Motherboard
*[GNOME]: GNU Network Object Model Environment
*[distro]: distribution of Linux - Linux kernel with bundled software
*[kernel]: Core of the operating system to manage hardware, memory and processes
*[downstream]: A distro built on top of another distro, inheriting its base

<!-- Alias -->
[fuck-microsoft]:   https://media1.tenor.com/m/-aZGk99QVM8AAAAd/space-force-microsoft.gif
[the-command-line]: workshop/the-command-line/temp.md

# Getting Started

**Welcome to Learn Unix Terminals. This page will get you set up and 
explain how the workshop works before you dive in.**

---

## Learning Linux

Most people associate the terminal and shells in a Unix-like system with 
Linux. You use the kernel, the core component to enable communication between 
hardware and software. Then different distros form the operating system with 
libraries and applications. The terminal is the most powerful skill any user 
of a Unix-like operating system can learn. Instead of being overwhelemed by the 
steep learning curve, this workshop teaches you the basics **interactively** 
to help understand why and how the terminal, shell and command-line work 
harmoniously together. You will learn the basics through different chapters 
which walk you through many different concepts. 

Too many users (and even developers) spend years avoiding the terminal. 
This workshop aims to fix that by teaching the basics of how to navigate files 
and directories, configure your system enviornment, and make use of CLI tools. 

***No prior experience is needed. Just a computer and a willingness to type.***

---

## Prerequisites

- [x] A computer running Linux, macOS, or Windows.
	* [ ] Using another OS? Why are you here?


---

## Setting Up Your Environment

!!! tip
    Increase your font size, you'll be staring at it a lot. Use: ++cmd+plus++ 
    **or** ++ctrl+shift+plus++

**You will need a terminal to follow along. Here is how to open one on each 
operating system:**

=== "Linux"

    I refuse to accept that you do not know the terminal. Search for 
    **Terminal** in your applications, or press ++ctrl+alt+t++ on most distros.

    Verify your shell:
    ```bash
    echo $SHELL #(1)!
    /usr/bin/bash #(2)!
    ```

    1. The `echo` command prints the value of the `$SHELL` variable.
    2. This is the expected output, your shell path. You might not have usr, 
    that is fine. You might see `/usr/bin/zsh`.

=== "macOS"

    Open **Terminal** from Applications &#8594; Utilities, or press 
    ++cmd+space++ and search for Terminal.

    Verify your shell:
    ```bash
    echo $SHELL #(1)!
    /bin/usr #(2)!
    ```

    1. The `echo` command prints the value of the `$SHELL` variable.
    2. This is the expected output, your shell path. You might have usr, 
    that is fine. You might see `/bin/bash`.

=== "Windows"

    Windows is a lot more challening due to the core design differences, 
    legacy and compatability, and most of all Microsoft has no insentive to 
    change. In addition, the command prompt in the Windows operating system is 
    absolutely terrible. So, you will be using something called WSL 2. 
    Installing this **will not** interfere with your normal Windows desktop, 
    but you will have a Linux operating system which has a command line and 
    filesystem. I personally reccomend that you use this virtual hard disk 
    file (starts small and automatically allocates, but does not shrink). 
    **Make sure to use version 2**. I recommend personally that you use the 
    Linux filesystem for all your programming and code related work.

    <div align="center">

    ![gif][fuck-microsoft] 

    </div>

    !!! info "Windows Version Required"
        These instructions require **Windows 10 or 11** in order to get 
	    WSL 2 and the Ubuntu shell up and running.

    - [x] **1. Run Windows Update**
        1. Open the **Start menu** and search for `Windows Update Settings`
    	2. Click **Check for updates**
    	3. Install any available updates and restart
	
    - [x] **2. Install WSL**
        1. Open the **Start menu** and search for `cmd.exe`
    	2. Right-click **Command Prompt** **&rarr;** **Run as administrator**
    	3. Run the following command and press ++enter++:
	```bash
	wsl --install
	```
		4. Restart your computer and confirm WSL is installed by 
		running in the **command prompt** the following:
	```bash
	wsl -l -v
	```
		!!! Warning "No distros installed"
			No need to panic if it says no distros are installed, 
			we will fix that.

    - [x] **3. Setting up the Ubuntu distro**
        1. In Command Prompt, run:  
	```bash
	wsl --install -d Ubuntu
	```
		2. A new Ubuntu window should open. If it doesn't, search for
		**Ubuntu** in the Start menu and launch it
		3. You'll be prompted to create a **username and password**

		!!! warning
			Your password **will not appear as you type**. 
			Make sure you remember these credentials for your 
			Linux user. Ubuntu only accepts lowercase usernames 
			by default.

    	!!! success
        	In the future, just search for the **Ubuntu** app in the start 
			menu to open it.

    - [x] **4. Test Your Setup**

		Once logged in, run:
		```bash
		echo "Hello world"
		```

		You should see `Hello world` printed to the console.
    ??? Abstract "What is [Ubuntu](https://ubuntu.com)?"
		It is one of the most popular Linux distributions and is what 
		you will be using throughout this course. It is a downstream 
		distro of Debian. I personally do not agree with their 
		philosophy of how they use the Debian project. Ubuntu is 
		developed by Canonical (for-profit), pushing proprietary 
		solutions and decisions that the open-source community is 
		strongly against. They force the GNOME desktop, Snap Packages, 
		additional bloat with sometimes a fragmented system. 
		It is still a massive improvement and is a good begineer 
		friendly OS with LTS. But, it is everything that the Linux 
		community strives against. It can be argued that Ubuntu is a 
		strong reason why many people who try Linux is immediately 
		turned off and leave. However, for the beginner purposes 
		of this workshop, this is what will be reccomended to be setup.

    ??? Failure "Where is the official WSL installation guide?"
		Microsoft's official guide is available at
		[aka.ms/wslinstall](https://aka.ms/wslinstall). Check if you
		missed any steps there.

    ??? Failure "Error: A required feature is not installed"
		You need to enable **Hyper-V (Virtualization)**:

		1. Open **Windows Features**
		2. Enable both **Hyper-V Management Tools** and
		**Hyper-V Platform**
		3. You may also need to enable virtualization in your **BIOS**

---

## How to Use This Tutorial

### Type the commands

**DO NOT COPY AND PASTE**. Type every command out yourself and it will 
feel slow. You need to start building muscle memory with your fingers. It is 
genuinely a real thing with the command-line.

### Reading the workshop formatting

**Code blocks**: commands to run in your terminal:
```bash
ls -la
```

**Inline code**: command names, flags, and file paths mentioned in text, 
like `ls`, `cd`, or `pwd`

**Keyboard shortcuts**: keys to press, like ++ctrl+c++ or ++tab++

**Admonitions**: callout boxes:

!!! note

!!! abstract

!!! tip

!!! warning
    These will not necessarily break anything, but ignoring them can 
    lead to unexpected results.

!!! danger
    Read carefully before running the command.

!!! info

!!! success

!!! question
    To test your understanding. Try to answer before moving on, if you cannot, 
    review the section again.

!!! failure
    A common mistake or error you might encounter, and how to fix it.

!!! example

!!! quote

### Expected output

When a command produces output, you will see it shown:

```bash
$ echo "hello"
hello
```

The `$` represents your terminal prompt, everything after it is the command. 
Lines without `$` are the expected output.

### If something goes wrong

- Typically press ++ctrl+c++ to cancel a running command
- Typically press ++ctrl+z++ to suspend a process
- Type `exit` to close a terminal session

---

## What to Expect

Each section of the tutorial will flow with a similar structure:

1. **Introduction** - what the topic is and why it matters
2. **Concepts** - the theory behind it, kept brief and practical
3. **Commands** - the key commands with examples
4. **Walkthrough** - exercises to practice
5. **Tips** - best practices and common gotchas
6. **Questions** - to check comprehension before moving on

---

[Start the Tutorial :lucide-arrow-right:][the-command-line]{ .md-button .md-button--primary }