Approximate time to complete: 1 minute

---
## Goal

Locate and open a hidden file in a directory, in which the password for bandit4 is located.

---
## Steps taken

1. **Change into the directory**: After checking for a directory called `inhere` using `ls`, I could use `cd` to change the current working directory to `inhere`. 
2. **Find the hidden file**: Using the command `ls -la` I listed all available files in this directory. The `-a` flag tells `ls` to also show hidden files, and I used the `-l` flag only for a more structured list view of the items. This way, I located a hidden file called `...Hiding-From-You` and opened it using `cat`, printing the password stored in it.

---
## Additional notes

- To hide files, one can simply start a directory or file name by a `.`, which marks it as hidden. I tried that on my local machine, which worked as intended. This is also the reason why the current working directory referenced by `.` and the directory above, called `..`, are not shown when using only `ls`.

---
## New insights and lessons learned

- **Hidden Files and Directories**: Even though a directory might seem empty when being looked up using `ls`, it might not be. When we are looking for something, we definitely should list also hidden items using the `-a` flag.
- **Relevance for Cybersecurity**: Attackers could hide files from victims. Whenever we try to locate files, it is important to also check hidden items, as they might include malicious files or "unexpected" directories and files. For example, a malware could store details in hidden files.

---
