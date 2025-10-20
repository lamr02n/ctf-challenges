Approximate time to complete: 2 minutes

---
## Goal

Find the file with human-readable content in a directory with 10 files to obtain the password for bandit5.

---
## Steps taken

1. **List all files**: I used `ls -l` to list all the files to check for possible differences. This step showed how many files I had to deal with, but provided no further information on the file types.
2. **Check the file contents using the `file` command**: I already knew that the command `file` can be used to check which type of file we work with. As the number of files in the directory was small and the filenames similar, I decided to use `file ./-file0*` with `*` being the number of the file. For every file, I then saw the content type. `-file00` was of type "PGP Secret Sub-key", and all files but one were simply "data". The only file with human-readable code (ASCII text) was `-file07`, which contained the password.

---
## Additional notes

- After completing this first try, I was not happy with the number of manual steps that I had to do, namely the repeated commands in the form `file ./-file0*`. For the low number of files in the directory this technique might have been sufficient, but for directories with more files this could become a problem. Therefore, I did some research to simplify the command(s) needed:
	- First, I replicated the exact steps again to find patterns in the structure of their output. For example, I noticed that the `find` command prints the "word" *ASCII*. When looking for human-readable file contents, I could simply filter by lines that include this word.
	- I did some research on *piping*, which can be used in Linux to feed the results of one command into another. My new command would simply replicate the steps that I did manually, and I came up with: `ls | file ./* | grep -i ascii`
	- `ls` prints all filenames, which would then be fed to the `file` command. With the asterisk, I could use the filenames as the filename argument for `file`. With the command `grep`, for which I also looked up the documentation, I could search for those entries containing the pattern "ascii". As it is difficult to know whether the pattern is printed in uppercase letters or not, I added the `-i` flag to make grep search for upper- and lowercase letters.
	- The command would then print `./-file07: ASCII text`, which contains the filename I was looking for.

---
## New insights and lessons learned

- **Usage of new commands**: I became more familiar with some comments that I have not used often in the past, namely `file` and `grep`. Additionally, I experimented with piping, which made me understand better how to quickly build more powerful commands.

---
