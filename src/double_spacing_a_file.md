
# Double space a file

This perl one-liner appends another newline character at the end of each line and then prints the line

```perl
perl -pe '$\ = "\n"' file
```

For example, if a file contains four lines:
```
line1
line2
line3
line4
```
By running the above one-liners we get the following output:
```
line1

line2

line3

line4
```
# Powershell Commands

```powershell
PS /root/projects/perl_one_liners/assignment> Get-Content ./space.txt                                     
1 A 3
1 A 3
1 A 3
1 A 3
1 A 3
1 A 3
1 A 3
PS /root/projects/perl_one_liners/assignment> (Get-Content ./space.txt | Out-String) -replace "`n", "`n`n"
1 A 3

1 A 3

1 A 3

1 A 3

1 A 3

1 A 3

1 A 3


PS /root/projects/perl_one_liners/assignment> 
```
