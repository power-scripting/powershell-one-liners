
# Shuffle all fields on each line

*Pomodoro: 4*

In this one-liner, the code to execute inside of the quotation marks is shuffle @F, which shuffles the fields and returns the shuffled list.

```perl
perl -MList::Util=shuffle -alne 'print "@{[shuffle @F]}"'
```

Let’s look at several examples to understand how to run the code inside the quotation marks.

```perl
$ echo a b c d | perl -MList::Util=shuffle -alne 'print "@{[shuffle @F]}"'
b c d a


$ echo a b c d | perl -MList::Util=shuffle -alne 'print shuffle @F'
bcda

$ echo a b c d | perl -MList::Util=shuffle -alne '$,=":"; print shuffle @F'
b:c:d:a
```
# Powershell Commands

I don't know how this will work but I did try some commands to replicate the output.

```powershell
PS /root> Get-Content ./word.txt                          
a b c d

PS /root> cat ./word.txt | %{$_.Split(" ")[1..3] + $_[0] }
b
c
d
a

PS /root> $var = (echo a b c d | %{$_.Split(" ")})   
PS /root> Write-Host $var[1..3 + 0]
b c d a
PS /root>

PS /root> echo a b c d | Sort-Object {Get-Random}
b
c
d
a

```