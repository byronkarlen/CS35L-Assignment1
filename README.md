# CS35L-Assignment1

This shell script is a "crude implementation of an English spelling checker." See the assignment spec below for more details. 


### Assignment Spec: 
Examine the file /usr/share/dict/linux.words, which contains a list of English words, one per line. Each word consists of one or more ASCII characters.
Sort this file and put the sorted output into a file sorted.words.

Then, take a text file containing the HTML in this assignment’s web page, and run the following commands with that text file being standard input. For each command tr, sort, comm, read the command’s man page and use that to deduce what the command should do given its operands here. Also, look generally at what each command outputs (in particular, how its output differs from that of the previous command), and why.

tr -c 'A-Za-z' '[\n*]'
tr -cs 'A-Za-z' '[\n*]'
tr -cs 'A-Za-z' '[\n*]' | sort
tr -cs 'A-Za-z' '[\n*]' | sort -u
tr -cs 'A-Za-z' '[\n*]' | sort -u | comm - sorted.words
tr -cs 'A-Za-z' '[\n*]' | sort -u | comm -23 - sorted.words
Let’s take the last command as the crude implementation of an English spelling checker. This implementation mishandles the input file sorted.words! Write a shell script named myspell that fixes this problem. Your script should read from standard input and output misspelled words to standard output, for a suitable definition of "words". The shell command:

myspell </usr/share/dict/linux.words
should output nothing, because the dictionary by definition contains only correctly-spelled words.

More info on the assignment here: 
https://web.cs.ucla.edu/classes/winter23/cs35L/assign/assign1.html 
