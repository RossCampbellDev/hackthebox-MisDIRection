# MisDIRection
"During an assessment of a unix system the HTB team found a suspicious directory. They looked at everything within but couldn't find any files with malicious intent".

## Find the flag
We are supplied with a not-so-hidden directory of mysterious files.

navigating to the directory (.secret - which can be revealed in linux GUI using ctrl-h) and then performing ls command shows us a list of directories. 

running `ls *` or `ls -R` gives us a more useful list, showing the files within (recursively going through them in a tree).  

what looks odd is that the directories are all single characters that build an alphabet (\[0-9\]\[a-Z\])

inside each directory is between 0 and n files that are always empty and their names are numbers.

I picked out the name of the parent directory for each number (e.g. file 2 would correspond to directory ‘F’ or whatever)

This gave me a 36 byte string.  I tried using hashcat to see if it would identify a hash, but this didn’t make sense as no hash formats are 36 bytes (usually 32 if near that size).

I then tried an online decoder - using UTF-8 or ASCII revealed the flag

#hackthebox #hacking #pentesting #exploitation
