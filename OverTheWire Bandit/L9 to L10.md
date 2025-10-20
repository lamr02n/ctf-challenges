Approximate time to complete: 5 minutes

---
## Goal

Find the password in the file `data.txt`. It is one of the few human-readable sequences and stands next to several "=" characters.

---
## Steps taken

1. **Research possibly helpful programs**: Before having a look at the file, I first checked which programs could allow me to find "human-readable" strings. After a bit of research and using the tips given as helpful programs beneath the task, I had found two options: 1. `grep` has a flag `-w` that can filter words or 2. the program `strings`, which filters by printable character sequences with a length of at least 4 characters. `strings` seemed more useful for this task, as I did not expect the password to be an actual word that a wordlist could find.
2. **Try out `strings`**: To use `strings`, I could simply pipe the lines into it: `cat data.txt | strings`. This left a number of lines, and I immediately saw something that looked like a password (due to its length and overall look). After scrolling through the file, I found several lines beginning with "=" characters, next to which a word was given. Combining the words from top to bottom, I got "the password{k is ...".

---
## New insights and lessons learned

- **New tool**: The program `strings` is definitely helpful for finding human-readable characters or strings in a file. In reverse engineering, I have often seen files that looked unreadable. Knowing that you can find readable sequences in these, such as string variables in a program execution, can be extremely powerful.

---
## Additional notes

- Scrolling through the results to find the lines starting with "=" was fine for the purpose of this task. However, after understanding the structure of the file, I think that it might be even better to additionally filter by lines that contain the "=" symbol, thereby using both hints. To do that, I tried to filter the results even more, for which I piped the result into `grep ==`, which gave me only the relevant lines. If there had been more lines being human-readable, this would have been even more important.
- *EDIT*: **Useful for searching for information in memory**: In a university CTF challenge, I came across printed memory contents. In this case, using the `strings` command helped me find the password I was looking for. This seems to be a very good use case for the tool.

---
