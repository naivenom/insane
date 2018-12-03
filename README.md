# Insanity notes

by [naivenom](https://ctftime.org/user/38647) `PKTeam`


# Web
### Local File Inclusion
Open the URL, after simple and quick directory bruteforcing we find a directory .git. We download the Index file: [http://18.191.227.167/.git/index](http://18.191.227.167/.git/index). We open that downloaded file using a Hex Editor and then we find an interesting folder/file!!

[http://18.191.227.167/crystalsfordays/traversethebridge.php](http://18.191.227.167/crystalsfordays/traversethebridge.php) The hint is saying Note2: I can't seem to remember the param. It's "file" We use that file parameter and exploit it. It is an LFI Vulnerability (Local File Inclusion).
![img](https://github.com/naivenom/insane/blob/master/pictures/1.png)

[http://18.191.227.167/crystalsfordays/traversethebridge.php?file=](http://18.191.227.167/crystalsfordays/traversethebridge.php?file=) We use this URL to exploit the vulnerability, and it becomes:
[http://18.191.227.167/crystalsfordays/traversethebridge.php?file=../../](http://18.191.227.167/crystalsfordays/traversethebridge.php?file=../../) We find too many files and the interesting one was TheEgg.html.

When we open that file: [http://18.191.227.167/crystalsfordays/traversethebridge.php?file=../../TheEgg.html](http://18.191.227.167/crystalsfordays/traversethebridge.php?file=../../TheEgg.html) we get the flag!

[Link](https://github.com/ImperiumCTF/Writeups/blob/master/TUCTF%202018/Web/Easter_Egg:_Crystal_Gate.md)
