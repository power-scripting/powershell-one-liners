# Find the numerically smallest element (minimum element) on each line

*Pomodoro: 3*

This one-liner uses the min function from `List::Util`. Once the line has been automatically split
by `-a` and the elements are in the `@F` array, the min function finds the numerically smallest element, which it prints.

```perl
perl -MList::Util=min -alne 'print min @F'
```

For example, if you have a file that contains these lines:

```
-8 9 10 5
7 0 9 3
5 -25 9 999
```
By running the above one-liners we get the following output:
```
-8
0
-25

```
# Powershell Commands

## File content:

```powershell
PS /root/projects/perl_one_liners/assignment> Get-Content ./number.txt
-8 9 10 5
7 0 9 3
5 -25 9 999
```
## Steps to re-create the output:

```powershell
PS /root/projects/perl_one_liners/assignment> $var = Get-Content ./number.txt
PS /root/projects/perl_one_liners/assignment> for ($i=0; $i -lt $var.Length; $i++) {
>> $var[$i] -split " " | Measure-Object -Minimum } 

Count             : 4
Average           : 
Sum               : 
Maximum           : 
Minimum           : -8
StandardDeviation : 
Property          : 

Count             : 4
Average           : 
Sum               : 
Maximum           : 
Minimum           : 0
StandardDeviation : 
Property          : 

Count             : 4
Average           : 
Sum               : 
Maximum           : 
Minimum           : -25
StandardDeviation : 
Property          : 


PS /root/projects/perl_one_liners/assignment>
```
