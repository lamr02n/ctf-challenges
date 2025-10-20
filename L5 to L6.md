Approximate time to complete: 5 minutes

---
## Goal

Find the file with the following properties and in it the password for bandit6:
- human-readable
- 1033 bytes in size
- not executable

---
## Steps taken

1. **Look up the documentation for `find`**: For the last challenge, I had used a combination of `ls`, `file` and `grep`, which didn't seem easily doable in this challenge. Therefore, I did research on the `find` command and found the option to input specific file sizes.
2. **Use `find` for the entire directory**: `find` searches all directories and subdirectories from a starting point. I used `find . -type f -size 1033c` in the `inhere` directory, which would specify the full `inhere` directory as starting point, also the type of the searched item and then the size. I decided to try only filtering by size first, which was enough to find only one file, which then also contained the password.

---
## New insights and lessons learned

- **Great tool for searching large areas**: `find` seems to be a very powerful tool for searching large directory trees. There are also many interesting and useful options that can be added to filter the results.

---
## Additional notes

- I decided at the beginning to first only filter by something that I could easily filter using the command at hand. As the size was very specifically given, I started with that. If this search had left me with more files, I could have added more options to filter, like `-executable`.
- The unit `c` in the size option for `find` stands for bytes.
- The additional flag `-type` was not necessary. However, this was the first interesting option that I found in the documentation and it filtered directories, which is also useful in this case, so I kept it for the remainder of the challenge.

---
