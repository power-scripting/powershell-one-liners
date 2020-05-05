
# Number words across all lines

*I spent 2 pomodoro on this task*

This perl one-liner finds each words and then numbers the word globally.

```perl
perl -pe 's/(\w+)/++$i.".$1"/ge'
```

For example, if you have a file with the following three lines:
```
just another
perl hacker
hacking perl code
```
By running this one-liner numbers each word in the file and produces the following output:

```
1.just 2.another
3.perl 4.hacker
5.hacking 6.perl 7.code

```
# Powershell Commands

I could number each line but not words.

```powershell
PS /root/projects/perl_one_liners/assignment> Get-Content ./regex.txt | ForEach { "{0} {1}" -f $_.ReadCount,$_ }
1 just another
2 perl hacker
3 hacking perl code
PS /root/projects/perl_one_liners/assignment>
```