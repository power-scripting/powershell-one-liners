
# Print the date 14 months, 9 days, and 7 seconds ago

*Pomodoro: 2*

## Perl One-liner
This one-liner modifies the first, fourth, and fifth elements of the `@now` list. The `mktime` command generates the UNIX time from this new structure, and localtime, which is evaluated in the scalar context, prints the date 14 months, 9 days, and 7 seconds ago.

```perl
perl -MPOSIX -le '
@now = localtime;
$now[0] -= 7;
$now[3] -= 9;
$now[4] -= 14;
print scalar localtime mktime @now
'
```

# Powershell Commands

I have created a function to return the output.

## File Content
```powershell
function Get-Newdate {
        [Cmdletbinding()]
        param(
                [Parameter(Mandatory=$true)]
                [int32]$addMonth,
                [Parameter(Mandatory=$true)]
                [int32]$addDay,
                [Parameter(Mandatory=$true)]
                [int32]$addSecond
        )
        $month = (Get-Date).AddMonths($addMonth)
        $day = $month.AddDays($addDay)
        $second = $day.AddSeconds($addSecond)
        Write-Host "The calculated date is " $second
}
```
## This is the output

```powershell
PS /root/projects> Get-Newdate         

cmdlet Get-Newdate at command pipeline position 1
Supply values for the following parameters:
addMonth: -14
addDay: -9
addSecond: -7
The calculated date is  03/07/2019 04:39:42
PS /root/projects>

PS /root/projects> Get-Newdate

cmdlet Get-Newdate at command pipeline position 1
Supply values for the following parameters:
addMonth: 14
addDay: 9
addSecond: 7
The calculated date is  07/25/2021 04:39:28
PS /root/projects>
```