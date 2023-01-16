# Installing Visual Studio Code
First, download Visual Studio Code for your operating system. The link to download it 
is [https://code.visualstudio.com/](https://code.visualstudio.com/). When VSCode is
open, it should look like this:
![Image](vscodewindow.png)

# Remotely Connecting
These steps are about how to connect to a remote computer using VS Code or a terminal.
1. Install git for Windows. The link is [https://gitforwindows.org/](https://gitforwindows.org/).
2. To have the default terminal use `git bash`, first open the terminal by pressing Ctrl + `. Press
Ctrl + Shift + P to open the command palette. Search "Select Default Profile", and select Git Bash. 
Then click "+" in the terminal window, the terminal will now be Git Bash.
3. Open the terminal, and type in the following command: `ssh cs15lwi23zzz@ieng6.ucsd.edu`. The "zzz"
will be the specific characters from your course account.
4. You will then see something like the following message. Type the command `yes` to the question.
```
⤇ ssh cs15lwi23zzz@ieng6.ucsd.edu
The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])?
```
5. After that, there will be a line like the following asking for the password.
```
(cs15lwi23zzz@ieng6.ucsd.edu) Password:
```
Type in the password and enter, even though it does not show up when it is being typed, it is still
being typed.

# Trying Some Commands
