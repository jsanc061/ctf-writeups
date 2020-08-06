Misc

## Where Can My Robot Go?
### Given: 
```
Where do robots find what pages are on a website?
Hint:
    What does disallow tell a robot?
```
Took the current URL, https://ctflearn.com/challenge/107 and replaced it with https://ctflearn.com/robots.txt

### Output 
```
User-agent: *
Disallow: /70r3hnanldfspufdsoifnlds.html 
CTFlearn{/70r3hnanldfspufdsoifnlds.html}
```

Navigated URL to https://ctflearn.com/70r3hnanldfspufdsoifnlds.html and found the flag.

### Flag: 
``` 
CTFlearn{r0b0ts_4r3_th3_futur3}
```

## Practice Flag
### Given: flag{CTFLearn_is_awesome}
### Flag: flag{CTFLearn_is_awesome}

## Reversal of Fortune
### Given:
```
Our team of agents have been tracking a hacker that sends cryptic messages to other hackers about what he's doing. We intercepted the below message he sent recently, can you figure out what it says? He mentions his hacker name in it, that's the code you need.

.nac uoy fi tIe$reveRpilF eldnah ym gnisu em egassem ,avaj yllacificeps ,gnidoc emos htiw pleh deen I ,deifitnedi tegrat txeN
```
### Output:
``` 
Next target identified, I need help with some coding, specifically java, message me using my handle FlipRever$eIt if you can.
``` 
### Flag:
```
CTFlearn{FlipRever$eIt}
```

## Wikipedia
### Given:
```
Not much to go off here, but it’s all you need: Wikipedia and 128.125.52.138. 
```
Navigated to https://www.wikipedia.org/ and entered the given IP address
This displayed all of the IP user's contributions to Wikipedia that included one post to 'Flag'
Navigated to through the Flag link and searched for 'CTF' which found the flag.

### Flag:
``` 
CTFlearn{cNi76bV2IVERlh97hP}
```

## QR Code 
### Given:
```
Do you remember something known as QR Code? Simple. Here for you : <br /> https://mega.nz/#!eGYlFa5Z!8mbiqg3kosk93qJCP-DBxIilHH2rf7iIVY-kpwyrx-0
```

Used Cyberchef to parse the QR Code
### Output:
``` 
c3ludCB2ZiA6IGEwX29icWxfczBldHJnX2RlX3BicXI=
```

Decyphered output string using base64
### Output:
``` 
synt vf : a0_obql_s0etrg_de_pbqr
```
Decyphered new string using ROT13 on cyberchef
### Output:
```
flag is : n0_body_f0rget_qr_code
```

### Flag:
``` 
CTFlearn{n0_body_f0rget_qr_code}
```

## QR Code V2
### Given:
```
How well are you in the ways of the QR Code? https://mega.nz/#!JItR3aqI!QKGxexShAPt-HUU_2DAdJKUljXc69sx1fXuaGUeoKaY
```
Parsed the QR Code using Cyberchef

### Output:
```
https://mega.nz/#!9NFhUbwQ!vtrLVum8z-ZXzur33RrGJ4uivMJhA9_5TW2ulHucXoU
```
Downloaded Flag.txt from the link 
### Flag:
``` 
CTFlearn{2_QR_4_U}
```

## IP Tracer
### Given:
```
Bob is an amateur hacker and has collected the following IP Address: 159.167.16.5, but Bob needs help finding where the IP Address is located. Can you help Bob find where the IP Address is located. (Type the City name)
```

Used https://www.iplocation.net/ to find IP's location
### Output:
``` 
London
```
### Flag:
``` 
CTFlearn{London}
```









