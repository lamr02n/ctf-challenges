Approximate time to complete: 2 minutes

---
## Goal

Open a file called `-` to obtain the password for bandit2.

---
## Steps taken

1. **Locating the file**: As in the previous level, after login via SSH I first had to check where I am (`pwd`) and which files are available (`ls`).
2. **Opening the file**: By using the `cat` command, I opened the file. However, the filename `-` had to be written as a path using `./-`. Entering the file the "normal" way, an empty screen would be printed and inputs from me would get awaited.

---
## Additional notes

- I first tried to use `"-"` and `'-'` to escape the filename. Some users on the internet also suggested the use of `--` before the file name. Both of these approaches did not work. In the first approach, the `"-"` seems to still be interpreted as `-`, because the same behavior is shown. The second approach also didn't work. On the internet I found no answers as to why this escape method would not work, because `--` indicates the end of command options, after which you should normally be able to enter something like a filename. The behavior is also still the same as with the other approaches, so I suppose that the interpretation is still the same as for `-`.
- Typing `cat -` leads to an input being expected. From what I have found online, `-` is an alias of STDIN, which explains the expected input.

---
## New insights and lessons learned

- **Escaping special filenames:** Different to the earlier level, the filename `-`could not be opened directly using `cat -`. This is because it is interpreted as a flag (which all start with `-`) and the system tries to find the flag that has been entered (which does not exist). This is a good reminder that some filenames can lead to problems with system functionalities. In this case, it could simply be escaped by using `./-`.
- **Relevance for Cybersecurity**: Some filenames can possibly overlap with system's functionalities. Not only will this lead to unexpected results for users (like not being able to open a file in a certain way), but attackers can use these filenames to trick the system into executing system functionalities.

---
