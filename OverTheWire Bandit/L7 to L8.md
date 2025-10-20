Approximate time to complete: 1 minute

---
## Goal

Find the password in a file, next to the word "millionth".

---
## Steps taken

1. **Checking out the file**: I first located the file, which was directly in the home directory, and checked it's contents using `cat`. As expected, a very large number of lines were printed. Here, I could see that each line started with an english word and was followed by a password-like sequence of characters. Every line consisted of only these two strings.
2. **Finding the word with `grep`**: As I already knew the command `grep`, with which you can search text for specific sequences, and had already seen pipes (`|`) earlier, I tried the command `cat data.txt | grep "millionth"`. This worked perfectly, and I got the line I was looking for.

---
## New insights and lessons learned

- **Relevance for Cybersecurity**: Although this was a very simple example of the potential of `grep`, it underscores how powerful the command is. An attacker could find sequences like passwords or keys in "hidden" places. An important lesson is that one should never store important and secret information in cleartext, as attackers might be able to find it in places we think they never search. There are tools that allow an attacker to find this information, if they know exactly what they are looking for.

---
