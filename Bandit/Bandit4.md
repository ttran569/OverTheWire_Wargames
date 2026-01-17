# Bandit 4
Bandit 4 command to login to ssh with username: bandit4, password: 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ, and port 2220 -> 

ssh -l bandit4 -p 2220 bandit.labs.overthewire.org

Bandit 4 to Bandit 5 commands to find and read contents of human-readable file in inhere folder: pwd for /home/bandit4 -> find to see all files in directory (lists from -file00 to -file09) -> to find which file is the human-readable one, use find /home/bandit4/inhere -type f -print0 | xargs -0 file | grep text to filter out the human-readable file (-type f filters for regular files, -print0 handles special filename characters by converting into null characters, xargs -0 file executes file command line from the filter input with separated null characters and identifies each file type, grep searches for files only containing readable text) -> -file07 is the human-readable file -> cat /home/bandit4/inhere/”-file07”

Contents of -file07 file -> password: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
