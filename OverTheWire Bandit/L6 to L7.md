Approximate time to complete: 3 minutes

---
## Goal

Find the file stored somewhere on the server and retrieve the password for bandit7. The file has given properties:
- owned by user bandit7
- owned by group bandit6
- 33 bytes in size

---
## Steps taken

1. **Change directory to `/` (root)**: With the file possibly being anywhere on the server, I first checked the home directory (which was empty) before I changed the directory to `/` (the root directory). This way, any following commands could search from `/`  as starting point, by which I can find any file on the server.
2. **Use `find` command to search file**: Using the `file` command, I could input the little information given as filter criteria: `find -user bandit7 -group bandit6 -size 33c 2>/dev/null`. Here, the `-user` , `-group` and `-size` flag are straightforward. The `2v/dev/null` is used to remove all `permission denied` errors.

---
## New insights and lessons learned

- **Removing error messages**: The `permission denied` errors were not helpful in this case, as I almost certainly knew that not many files have exactly size 33 bytes. Therefore, it was necessary to turn them off. With the argument provided, I managed to get a clear view of what I was looking for, which might be very useful whenever I work with similar outputs.

---
## Additional notes

- Without the `2>/dev/null` argument, the screen is full with `permission denied` errors for files I do not have access to. They are shown, no matter if they comply with the criteria set. On the internet, I found this solution which worked perfectly for this case. The only file shown would then be the one I was looking for.

---
