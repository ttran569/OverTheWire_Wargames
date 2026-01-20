# Bandit 13
Bandit 13 command to login to ssh with username: bandit13, password: FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn, and port 2220 -> 

**ssh -l bandit13 -p 2220 bandit.labs.overthewire.org**

Bandit 13 to Bandit 14 commands to use sshkey.private from Bandit 13 to get Bandit 14 password: use on main terminal **scp -P 2220 bandit13@bandit.labs.overthewire.org:sshkey.private .** 
(scp -P uses the port connection since it’s required to connect to bandit13, the format is username@hostname:<remotefiletocopy> destination) -> **bandit13@bandit.labs.overthewire.org:sshkey.private .**, . represents the current directory which is also the destination for the copied sshkey.private file) to get the sshkey.private file by copying it into our system [sshkey.private file is a private SSH key that can be used to get into servers without needing to know the password of the user] -> chmod 600 sshkey.private (chmod 600 adds extra authentication by reducing permissions of the private key needed for bandit14@bandit.labs.overthewire.org to accept the private key) -> use ssh -i sshkey.private -p 2220 bandit14@bandit.labs.overthewire.org to login as the user bandit14 without knowing the password

Contents of /etc/bandit_pass/bandit14 file: password: MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
