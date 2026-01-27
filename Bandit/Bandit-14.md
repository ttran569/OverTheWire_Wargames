# Bandit 14
Bandit 14 command to login to ssh with username: bandit14, password: <from Bandit 13>, and port 2220 -> 

**ssh -l bandit14 -p 2220 bandit.labs.overthewire.org** ***/*** **ssh -i sshkey.private -p 2220 bandit14@bandit.labs.overthewire.org**

Bandit 14 to Bandit 15 commands to get password from port 30000 on localhost: change directory by using **cat /etc/bandit_pass/bandit14** to read the password on the bandit14 file -> **nc localhost 30000** ***or*** **telnet localhost 30000** (nc or netcat connects localhost to port 30000 to submit the Bandit14 password by listening for port 30000; telnet communicates with the port using the TELNET protocol; format is nc [destination/host] [port] / telnet [host] [port])

