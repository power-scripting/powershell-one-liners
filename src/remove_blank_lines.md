# Remove all blank lines


This perl one-liner appends another newline character at the end of each line and then prints the line

```perl
perl -ne 'print unless /^$/'
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
PS /root/projects/perl_one_liners/assignment> Get-Content ./a.txt
1 A 3

1 A 3

1 A 3

1 A 3

1 A 3

1 A 3

1 A 3

PS /root/projects/perl_one_liners/assignment> Get-Content ./a.txt | where {$_ -ne ""}
1 A 3
1 A 3
1 A 3
1 A 3
1 A 3
1 A 3
1 A 3
PS /root/projects/perl_one_liners/assignment>
```
