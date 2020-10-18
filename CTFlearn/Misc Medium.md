Misc Medium

## What could this be?
### Given:
```
It seems like someone really likes special characters… Or could it mean something more? https://mega.nz/#!SDQkUYQZ!b1Fu7iZ_wGiNX0aOjez95_74TYDCnLb3YSQfRzs0J-o
```
The link downloads a file name ``` what_can_this_be.txt ```
Using the website, https://enkhee-osiris.github.io/Decoder-JSFuck/, this text can be decoded to give the flag output by copying and pasting the file's information on this site. 
This gives us the final output for the flag.
### Output:
``` 
alert("flag{5uch_j4v4_5crip7_much_w0w}")
```
### Flag:
``` 
CTFlearn{5uch_j4v4_5crip7_much_w0w}
```

## Ambush Mission
### Given:
```
Hi, i can't tell you my name since now i'm in a mission. In case to arrest our fugitive target, our team had been intercepted communication between the target with his fellow and found this image (https://mega.nz/#!TKZ3DabY!BEUHD7VJvq_b-M22eD4VfHv_PPBnW2m7CZUfMbveZYw). It looks like they are going to meet in specific place, but we still don't know the time yet. Can you help me?
```
The link downloads a file named ``` clue.png ```

Used the following website to browse the image's bit planes, https://stegonline.georgeom.net/upload
While viewing the ``` Red 0 ``` bit plane, an encoded string is found. 
```
==QTh9lMx8Fd08VZt9FdFNTb
```
This string looks similar to base64, but the equal signs are reversed and placed at the beginning of the string. 
Used a reverse text website to flip the string, http://www.textreverse.com/ to get a base 64 string output.
```
bTNFdF9tZV80dF8xMl9hTQ==
```
Then we can use the base64 decode command to read the string:
```
echo 'bTNFdF9tZV80dF8xMl9hTQ==' | base64 -d
```
### Output:
``` 
m3Et_me_4t_12_aM%
```
### Flag:
``` 
CTFlearn{m3Et_me_4t_12_aM}
```