# Bandit 6
Bandit 6 command to login to ssh with username: bandit6, password: HWasnPhtq9AVKe0dmk45nxy20cvUa6EG, and port 2220 -> 

**ssh -l bandit6 -p 2220 bandit.labs.overthewire.org**

Bandit 6 to Bandit 7 commands to find and read contents of file with given properties (owned by user bandit7, owned by group bandit6, 33 bytes in size): Use **find / -user bandit7 -group bandit6 -size 33c -print0 | xargs -0 file | grep text** to search through the entire server file system (/ represents root directory of server filesystem, compared to . being current directory; -user bandit7 to specify which user owns the file, -group bandit6 to specify which group owns the file, -size 33c to specify 33 byte size) -> **cat /var/lib/dpkg/info/bandit7.password**
