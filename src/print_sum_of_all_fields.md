
# Print the sum of all fields on each line

*Pomodoro: 2*

This one-liner turns on field auto-splitting with the -a command-line option and imports the sum function from the List::Util module with -Mlist::Util=sum.

```perl
perl -MList::Util=sum -alne 'print sum @F'
```

For example, the line 1 4 8 would be split on each space so that @F would become `(1, 4, 8)`. The sum `@F` statement sums the elements in the `@F` array, giving you 13.

```
1 2 3 4 5 6 7 8 9 10
```
By running the above one-liners we get the following output:
```
The output is 55 because that’s the sum of the numbers 1 through 10.
```
# Powershell Commands

```powershell
PS /root/projects/perl_one_liners/assignment> Get-Content ./number.txt
1 2 3 4 5 6 7 8 9 10

PS /root/projects/perl_one_liners/assignment> Get-Content ./number.txt | %{$_.Split(" ")}
1
2
3
4
5
6
7
8
9
10


PS /root/projects/perl_one_liners/assignment> Get-Content ./number.txt | %{$_.Split(" ")} | Measure-Object -AllStats

Count             : 10
Average           : 5.5
Sum               : 55
Maximum           : 10
Minimum           : 1
StandardDeviation : 3.02765035409749
Property          : 


PS /root/projects/perl_one_liners/assignment>
```
