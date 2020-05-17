
# Calculate the factorial

*Pomodoro: 2*

## Perl One-liner
This one-liner uses the `bfac()` function from the `Math::BigInt` module in the Perl core.

```perl
perl -MMath::BigInt -le 'print Math::BigInt->new(5)->bfac()'
```
Another way to calculate a factorial is to multiply the numbers from 1 to n together. Here, `$f` is set to 1 and then loop from 1 to 5 and multiply `$f` by each value. The result is `120 (1*2*3*4*5)`, the factorial of `5` .

```perl
perl -le '$f = 1; $f *= $_ for 1..5; print $f'
```

# Powershell Commands

I have created a function to return the output.

## File Content
```powershell
function Get-Factorial {
        [Cmdletbinding()]
        param(
                [Parameter(Mandatory=$true)]
                [int32]$number
        )
    if($number -lt 0)
    {
        $result = 0
    }
    elseif($number -le 1)
    {
        $result = 1
    }
    else
    {
        $result = $number * (Get-Factorial($number - 1))
    }
    return $result
}
```
## This is the output

```powershell
PS /root/projects/perl_one_liners/factorial> Get-Factorial

cmdlet Get-Factorial at command pipeline position 1
Supply values for the following parameters:
number: 5
120


PS /root/projects/perl_one_liners/factorial> Get-Factorial 8
40320
PS /root/projects/perl_one_liners/factorial>
```