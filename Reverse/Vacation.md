# Vacation

**Category: REVERSE**

**Description:**

>My friend told me they were going on vacation, but they sent me this weird PowerShell script instead of a postcard!

### Solving the challenge

We have this powershell script :

```powershell
$bytes = [System.Text.Encoding]::ASCII.GetBytes((cat .\flag.txt))
[System.Collections.Generic.List[byte]]$newBytes = @()
$bytes.ForEach({
    $newBytes.Add($_ -bxor 3)
    })
$newString =  [System.Text.Encoding]::ASCII.GetString($newBytes)
echo $newString | Out-File -Encoding ascii .\output.txt
```
And the following output file :

```
m33ayxeqln\sbqjp\twk\{lq~
```

I've tried to reverse the process :

![Solve](/images/Vacation.JPG)

And we have the flag !

### Flag

```n00bz{from_paris_wth_xor}```
