# ask
A linux - bash command line tool for prompting with an llm 

## EXAMPLE USAGES
```bash
[bk@bk ask]$ top -b -o %MEM -n 1 | head -n 20 | ask "find the highest memory consuming process"
1771 bk        20   0   49,4g 532208 346296 S   0,0   3,3   0:30.81 brave

[bk@bk ask]$ ./ask what is the capital of france
Paris

[bk@bk ~]$ ls | ask "Do I have a folder called Git-Projects ?"
Yes, you have a folder called Git-projects.

[bk@bk ask]$ git diff --staged | ask "Write a concise, conventional commit message for these changes"
fix: improve code readability and simplify logic

[bk@bk ask]$ ask what is the command used to extract tar files
tar -xvf filename.tar

[bk@bk ask]$ alias wth="ask 'Explain what this linux command does in simple terms'"
[bk@bk ask]$ wth tar -czvf archive.tar.gz /myfolder
Creates a compressed archive (archive.tar.gz) of the contents in /myfolder.

- c: create
- z: compress
- v: show progress
- f: output file name
```

## Known Limitations
**Token-limit:** If the given input is too large in terms of size it does not return any output due to prompt token limit.
