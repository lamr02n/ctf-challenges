Approximate time to complete: 1 minute

---
## Goal

Locate the file on bandit0's home directory, open it and obtain the password for bandit1.

---
## Steps taken

1. **Locating the home directory**: Using the command `pwd` I checked where on the system I am. Although after login with SSH you often start in the user's home directory, the behavior might have been reconfigured on the host. The file `readme` was directly located in the current working directory, which I could check using the `ls`  command to list all files.
2. **Opening the file**: By using `cat` I opened the file `readme`. The password was not hidden in the file and could be directly copied. I stored the password in a file on my local machine to have it ready if needed in the future.
3. **Log in with user bandit1**: Using SSH, like in Level 0, I logged into the same host using the username bandit1.

---
## New insights and lessons learned

- **Storing relevant information**: To collect and store any credentials or other important notes, I created a text file on my local machine. This way, I can copy and paste passwords for the levels whenever needed. Having a central file for that helps to keep an overview.
- The use of `pwd`, `ls` and `cat` is well known due to my background.
- **Relevance for Cybersecurity**: Knowing the essential commands for Linux systems is mandatory for checking where on a remote machine one is and how to list and open files.

---
