Crypto Easy

## Character Encoding
### Given:
``` 
41 42 43 54 46 7B 34 35 43 31 31 5F 31 35 5F 55 35 33 46 55 4C 7D
```

Converted from Hex to get the following output
### Output:
```
ABCTF{45C11_15_U53FUL}
```
### Flag:
```
CTFlearn{45C11_15_U53FUL}
```

## Hextroainary
### Given:
``` 
Meet ROXy, a coder obsessed with being exclusively the worlds best hacker. She specializes in short cryptic hard to decipher secret codes. The below hex values for example, she did something with them to generate a secret code, can you figure out what? Your answer should start with 0x.

0xc4115 0x4cf8
```
Used a XOR calculator to add the two hex values together to get:
### Output:
``` 0xC0DED ```

### Flag:
```
CTFlearn{0xC0DED}
```

## Base 2 2 the 6
### Given:
```
There are so many different ways of encoding and decoding information nowadays... One of them will work! Q1RGe0ZsYWdneVdhZ2d5UmFnZ3l9
```
Decoded the given string using Base64 
### Output:
```
CTF{FlaggyWaggyRaggy}
```
### Flag:
``` 
CTFlearn{FlaggyWaggyRaggy}
```

## Bruxor
### Given:
```
There is a technique called bruteforce. Message: q{vpln'bH_varHuebcrqxetrHOXEj No key! Just brute .. brute .. brute ... :D
```
Used Cyberchef to brute force XOR the message string
Found the flag at Key = 17
### Output 
```
flag{y0u_Have_bruteforce_XOR}
```
### Flag:
``` 
CTFlearn{y0u_Have_bruteforce_XOR}
```

## Reverse Polarity
### Given:
```
I got a new hard drive just to hold my flag, but I'm afraid that it rotted. What do I do? The only thing I could get off of it was this: 01000011010101000100011001111011010000100110100101110100010111110100011001101100011010010111000001110000011010010110111001111101
```

Used Cyberchef to decode from binary
### Output:
```
CTF{Bit_Flippin}
```
### Flag:
``` 
CTFlearn{Bit_Flippin}
```

## Vigenere Cipher
### Given:
```
The vignere cipher is a method of encrypting alphabetic text by using a series of interwoven Caesar ciphers based on the letters of a keyword.<br />

I’m not sure what this means, but it was left lying around: blorpy

gwox{RgqssihYspOntqpxs}

```
### Output:
``` 
flag{CiphersAreAwesome}
```
### Flag:
``` 
CTFlearn{CiphersAreAwesome}
```


## Morse Code 
### Given:
```
..-. .-.. .- --. ... .- -- ..- . .-.. -- --- .-. ... . .. ... -.-. --- --- .-.. -... -.-- - .... . .-- .- -.-- .. .-.. .. -.- . -.-. .... . . ...
```
### Output:
``` 
FLAGSAMUELMORSEISCOOLBYTHEWAYILIKECHEES
```
### Flag:
``` 
CTFlearn{FLAGSAMUELMORSEISCOOLBYTHEWAYILIKECHEES}
```

## HyperStream Test #2
### Given:
```
I love the smell of bacon in the morning! ABAAAABABAABBABBAABBAABAAAAAABAAAAAAAABAABBABABBAAAAABBABBABABBAABAABABABBAABBABBAABB
```
Used Bacon Cipher on Cyberchef to decode the string set with A/B for translation
### Input:
```
ABAAAABABAABBABBAABBAABAAAAAABAAAAAAAABAABBABABBAAAAABBABBABABBAABAABABABBAABBABBAABB
```
### Output:
``` 
ILOUEBACONDONTYOU
```
### Flag:
``` 
CTFlearn{ILOUEBACONDONTYOU}
```

















