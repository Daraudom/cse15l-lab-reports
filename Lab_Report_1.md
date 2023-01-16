# Lab Report 1
This tutorial will make sure that you're competent in executing the following tasks:
1. Installing VSCode
2. Remotely Connecting
3. Running Commands

> If on Windows, make sure to install GitBash since this will be the primary language used in the terminal.
---
## Installing VS Code
1. Head to the [link here](https://code.visualstudio.com/) to download and install the **latest version** of VSCode on your laptop. Make sure it's the right operating system.
2. Once installed, locate VScode in your file explorer (Windows) or Finder (MacOS) and open it. You should see the following:
![Image]()
## Remotely Connecting 
1. First, retrieve your course-specific account for CSE 15L [here](https://sdacs.ucsd.edu/~icc/index.php). Enter the necessary information as prompted.
2. Follow this [tutorial](https://docs.google.com/document/d/1hs7CyQeh-MdUfM9uv99i8tqfneos6Y8bDU0uhn1wqho/edit) to change the password for CSE 15L. There should be a 15 minutes grace period before the password is fully in the system. In my case, it worked instantly but if it doesn't, do wait.
3. Go to VScode and open a terminal. Type `ssh`. Your command should look like the following, but with 'ABC' replaced by the letters in your course-specific account.

`$ ssh cs15lwi23ABC@ieng6.ucsd.edu`

4. Since this will be your first time connecting to the server, the following message will most likely pop up:

```
$ ssh cs15lwi23ABC@ieng6.ucsd.edu
The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])? 
```
5. Make sure to type **yes** and hit enter. You will be prompted to give a password. Type your password and hit enter.
6. Overall, the entire process should resemble the following image. Keep in mind that this was done on a Windows laptop.
![Image]()
