# Bandit 5
Bandit 5 command to login to ssh with username: bandit5, password: <from Bandit 4>, and port 2220 -> 

**ssh -l bandit5 -p 2220 bandit.labs.overthewire.org**

Bandit 5 to Bandit 6 commands to find and read contents of file with given properties (human-readable, 1033 bytes in size, not executable): **pwd** for /home/bandit5 -> **find** to see all files in directory (huge list) -> to specifically find the file given the properties, use **find /home/bandit5/inhere -type f -size 1033c -not -executable -print0 | xargs -0 file | grep text** (-size 1033c to specify the 1033 byte size and the c is required to focus on bytes, -not -executable to specify the file isn’t executable) -> /maybehere07/.file2 is given as the only file (1000 byte size is close to 1033?) -> **cat /home/bandit5/inhere/maybehere07/.file2**

