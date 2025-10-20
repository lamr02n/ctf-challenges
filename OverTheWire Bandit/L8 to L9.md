Approximate time to complete: 2 minutes

---
## Goal

Find the password in the file `data.txt` in the only line of text that occurs only once.

---
## Steps taken

1. **Checking the file structure**: As usual, I first looked at the contents of the file. I could see that each line contained only the password-like string sequence and no more information.
2. **Looking up the documentation for `uniq`**: The program `uniq` was mentioned as one of the potentially useful programs for this task. Due to its name, I figured it could help in this task, and therefore checked out the documentation. I found that it indeed filters duplicate lines, and also found a command that I could use for printing only line that exist only once.
3. **Try out command**: I used the command `sort data.txt | uniq -u` that I found, and it gave me exactly the one password I was looking for.

---
## New insights and lessons learned

- **New Tool**: `uniq` is another very helpful tool for finding information in big files. Although it might have limited use cases, it was very helpful to find that many such tools exist for these very specific purposes.

---
## Additional notes

- **What does the command do?**: The command first sorts the lines in the file. When piping the result into `uniq`, the sorted lines are filtered such that only one of each is shown. However, for this task I needed to show not just one of each, but only those that exist exactly once. For this, the `-u` flag can be used.
- **Would `cat data.txt | uniq -u` also work?** The answer is *no*. I tested the command without sorting the contents first, and found that it requires lines to be directly after one another to filter them. It does not apply sort itself.

---
