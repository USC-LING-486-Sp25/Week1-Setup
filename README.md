# LING 486 Natural Language Processing
___
## Introduction
Welcome to the Spring 2025 offering of LING 486, Natural Language Processing, with Professor Khalil Iskarous.

This repository is part of a larger organization called [USC-LING-486-Sp25](https://github.com/USC-LING-486-Sp25) which may contain other resources for the course.

Specifically, this `repository` (you can think of this as a Google Drive Folder) contains the setup instructions for Week 1 of this course.
___
## Steps to Success
# Table of Contents

1. [Introduction](#introduction)
2. [Steps to Success](#steps-to-success)
3. [Setting Up Your IDE](#setting-up-your-ide)
   - [Background: What is an "IDE"? (Optional)](#background-what-is-an-ide-optional)
   - [Download Link](#download-link)
4. [Downloading Libraries](#downloading-libraries)
   - [A. Background: What is a Library? (Optional)](#a-background-what-is-a-library-optional)
   - [B. Creating a Virtual Environment](#b-creating-a-virtual-environment)
     - [Step 1: Verify your Python version](#step-1-verify-your-python-version)
     - [Step 2: Create a Virtual Environment](#step-2-create-a-virtual-environment)
     - [Step 3: Verify your Virtual Environment](#step-3-verify-your-virtual-environment)
   - [C. Download Dependencies](#c-download-dependencies)
     - [Option 1: Downloading with Requirements.txt (recommended)](#option-1-downloading-with-requirementstxt-recommended)
     - [Option 2: Downloading Manually](#option-2-downloading-manually)
     - [Verify Installation](#verify-installation)
5. [Setting up a Github Account (Optional)](#setting-up-a-github-account-optional)
   - [Prerequisites](#prerequisites)
   - [Clone Repo to your Computer](#clone-repo-to-your-computer)

As a quick overview, this guide will help you install (1) Visual Studio Code, an Integrated Development Environment (IDE), and (2) the appropriate steps for running modern machine learning libraries directly on your computer!
- There may be some hiccups along the way but don't worry, these are all part of the process!

Note: If you do not already have a Github account and SSH key setup on your computer, you may follow the steps detailed [here](#setting-up-a-github-account-optional)
___
## Setting Up Your IDE
### Background: What is an "IDE"? (Optional)
- IDE or Integrated Development Environment is an application (like Google Chrome, Slack, or Zoom on your computer) that provides a:
	1. File Explorer
	2. Terminal
	3. Code Editor
- What makes an IDE truly "integrated" is that all of these 3 tools (and more if you're interested in playing around with it) are packaged into one download
	- Here for more [background](https://en.wikipedia.org/wiki/Integrated_development_environment)

### Download Link
- Select your Operating System (likely Windows or Mac): https://code.visualstudio.com/download
- Below are videos on how to setup VsCode including the helpful `code .` shortcut
	- [Mac](https://www.youtube.com/watch?v=w0xBQHKjoGo)
	- [Windows](https://www.youtube.com/watch?v=cu_ykIfBprI)
- Optional but recommended:
	- Feel free to add these [VsCode Extensions](https://marketplace.visualstudio.com/vscode): Python, Pylance, Autopep8 
	- Feel free to change the [theme](https://code.visualstudio.com/docs/getstarted/themes#:~:text=Select%20the%20File%20%3E%20Preferences%20%3E%20Theme,you%20want%20and%20press%20Enter.) or visual appearance of your editor
___
## Downloading Libraries
### A. Background: What is a Library? (Optional)
- Seldom do programmers write code completely from scratch, rather they use code written by other programmers known as "libraries"
- The libraries that we are going to be using for week 1 is:

| Library Name                                                      | Description                                                                                                                                                                                                                                                                                                            |
| ----------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Pytorch](https://pytorch.org)                                    | A library that contains the fundamental building blocks needed for Machine Learning algorithms originally developed by Meta AI                                                                                                                                                                                         |
| [Transformers](https://huggingface.co/docs/transformers/en/index) | A library that contains fundamental building blocks for [`transformer` architecture](https://arxiv.org/abs/1706.03762) which most modern Natural Language Processing (NLP) models are built on. <br><br>Developed and maintained by HuggingFace.<br><br>Requires a base machine learning library like `Pytorch` to run |
### B. Creating a Virtual Environment
- When downloading libraries, its often highly recommended (and in fact mandatory for new Macs), to download all of your libraries to a `virtual environment`
- A `virtual environment` is a copy of your computer's python library and stores your downloaded libraries
	- This way, if you make a mistake or need to reinstall your libraries (often called a clean reinstall) this is as simple as deleting the `virtual environment` folder you are about to create
- Note: `virtual environments` are often called `venvs` for short

#### Step 1: Verify your Python version
1. Open a [terminal in VsCode](https://code.visualstudio.com/docs/terminal/getting-started#:~:text=To%20get%20started%20with%20the,Bash%2C%20PowerShell%2C%20or%20Zsh.)
	![[assets/Terminal_Example.png]]
1. Check your Python Version
```
python3 -V
```
Ex output:
```
Python 3.8.10
```
- Note: some computer's require you to type `python3` since the default version of python installed on your computer is `python2` which is not new enough for `Pytorch` and `Transformers`
	- This guide is completed using `python3.8.10`, if you have any issues, making sure you're python version is `>=3.8.10` will help insure your Python version is not causing issues
#### Step 2: Create a Virtual Environment
1. In your desired "workspace" (where you will be programming), create a `Virtual Environment`
```
python3 -m venv .venv
```
- Explanation (optional):

| Command Component | Description                                                        |
|-------------------|--------------------------------------------------------------------|
| `python3`         | Uses the version of Python 3 listed above                         |
| `-m`              | Executes a command rather than running a Python program          |
| `venv`            | Executes the "create virtual environment" command                |
| `.venv`           | The name of your virtual environment (can be called anything, e.g., `my_venv`) |

2. Activate the `venv`
Mac/Linux
```
source .venv/bin/activate
```
Windows
```
.env/Scripts/activate
```
#### Step 3: Verify your Virtual Environment
- After activating the `venv`, we can verify that your Python commands will be executed using your new virtual environment
- Below, we can verify which version of Python your terminal is referring to

Linux/Mac:
```
which python
```
Windows
```
where python
```

Ex result:
- As long as you see the folder name (for ex `Week1-Setup`) and then `.venv/bin/python` this means you're successfully using your `venv`
```
/Users/{YOUR_USER_NAME}/Folder1/Folder2/A_LING_486/guides/Week1-Setup/.venv/bin/python
```
### C. Download Dependencies
#### Option 1: Downloading with Requirements.txt (recommended)
- Download the [`requirements.txt`](https://github.com/USC-LING-486-Sp25/Week1-Setup/blob/main/requirements.txt) or optionally have cloned the repository (see step [here](#setting-up-a-github-account-optional))
```
pip install -r requirements.txt
```
#### Option 2: Downloading Manually
```
pip install numpy pytorch transformers
```

### Verify Installation
- Download the [`verify_installations.py`](https://github.com/USC-LING-486-Sp25/Week1-Setup/blob/main/verify_installations.py) or optionally have cloned the repository (see [here](#setting-up-a-github-account-optional))
```
python3 verify_installations.py 
```
Expected output:
```
Successfully downloaded Pytorch Version: 2.4.1
Successfully downloaded Transformers Version: 4.46.3
```
- Note: if you do not see the "successfully downloaded" this means the libraries were not downloaded successfully
___
## Setting up a Github Account (Optional)
- Github, where these instructions live, contains "repository" representing version controlled folders containing code, input files, and instructions (like this one!)

### Prerequisites
- To `clone` this repository (create a copy), you need to create a (1) Github account and (2) an SSH key for your local computer

1. Create a Github Account
	1. https://github.com
2. Install Git
	1. https://github.com/git-guides/install-git
3. Create an SSH Key
	1. https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

### Clone Repo to your Computer
In your desired folder on your computer, open a `terminal` and run
```
git clone git@github.com:USC-LING-486-Sp25/Week1-Setup.git
```