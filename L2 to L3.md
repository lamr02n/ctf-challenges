Approximate time to complete: 1 minute

---
## Goal

Open a file called `spaces in this filename` to obtain the password for bandit3.

---
## Steps taken

1. **Opening the file**: I opened the file using the command `cat "spaces in this filename"`.

---
## Additional notes

- After opening the file with the method described above, I tried several other methods, which all worked as well. I have often used `\` to escape empty characters, so I knew that this would work. For filenames with spaces, the method I tried in the earlier Level 1 -> Level 2 (escaping with `"..."`) works as well. Specifically, I tried:
	- `cat 'spaces in this filename'`
	- `cat spaces\ in\ this\ filename`
	- `cat .\spaces\ in\ this\ filename`

---
## New insights and lessons learned

- **Better understanding of escaping filenames**: I tried several methods of opening the file, which all worked. This helped me better understand which methods can be used.

---
