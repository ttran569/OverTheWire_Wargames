# Bandit 12
Bandit 12 command to login to ssh with username: bandit12, password: 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4, and port 2220 -> 

**ssh -l bandit12 -p 2220 bandit.labs.overthewire.org**

Bandit 12 to Bandit 13 commands to find and read contents of hexdump file compressed multiple times: **mktemp -d** (to make a unique temporary directory in /tmp) -> cp data.txt {/tmp directory created} (copies the file to the directory) -> **cd** {/tmp directory created} -> **xxd -r data.txt data.bin** (xxd -r reverts the hexdump into a binary file) -> since the file was compressed multiple times through various compression methods, a bash script is useful in decompressing the multiple methods (gzip, bzip2, tar); to run the bash script on the terminal, use **chmod +x script_name.sh** -> **./script_name.sh data.txt** (below is the script to check through each compression method:
#!/bin/bash

file="$1"

if [ -z "$file" ] || [ ! -f "$file" ]; then
    echo "File doesn't exist"
    exit 1
fi

while true; do
    type=$(file "$file")
    echo "Processing: $file"
    echo "Detected: $type"
    printf '=%.0s' {1..50}; echo

    if echo "$type" | grep -q "gzip compressed data"; then
        next_file="${file}_unzipped"
        gunzip -c "$file" > "$next_file"
        rm "$file"
        file="$next_file"

    elif echo "$type" | grep -q "bzip2 compressed data"; then
        next_file="${file}_unzipped"
        bunzip2 -c "$file" > "$next_file"
        rm "$file"
        file="$next_file"

    elif echo "$type" | grep -q "POSIX tar archive"; then
        extracted_file=$(tar -tf "$file")
        tar -xf "$file"
        rm "$file"
        file="$extracted_file"

    else
        echo "Original file reached: $file"
        file "$file"
        break
    fi
done
Contents of data8.bin_unzipped file found from decompressing hexdump file -> password: FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
