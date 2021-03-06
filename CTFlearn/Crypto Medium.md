Crypto Medium

## Substitution Cipher
### Given:
```
Someone gave me this, but I haven't the slightest idea as to what it says! https://mega.nz/#!iCBz2IIL!B7292dJSx1PGXoWhd9oFLk2g0NFqGApBaItI_2Gsp9w Figure it out for me, will ya?
```
The link downloaded a file named ``` Substitution.txt ```
Using the name of this challenge as a hint, I searched for different substitution cipher decoders until this one was found: https://planetcalc.com/8047/ and pasted the file's text to decrypt it.
After waiting a few moments, the output was finally unencrypted:
### Output:
``` 
THE FLAG IS IFONLYMODERNCRYPTOWASLIKETHIS. GENERATED BY MARKOV CHAIN OF THE WIKIPEDIA PAGE ON CALVIN AND HOBBES. BE WERE LONG, THE FLAWS ON A 2005 PRESENT TIMES THAN STAMINA OR A WEEKLY SUNDAY, DECEMBER 21, 1989 1990, THE DREW EDITORS WAS UPROOTED EVERY WORLD CAN BE FOUND THE CONTINUED TO WORK AT A FAITHFUL REPLIES WHERE HOBBES, STYLE AIM CALVIN, ATTACK BOTH SIDES TO MARKS, "WHAT DO CONTROLLING AN ACTUAL BOARD BOXES IN THE PREPARENTS NAME, IS IMPULSIVE RAMPAGES IN WHICH ALWAYS REFERENCES THE PASSWORD, WHICH MONEY, AND THEY HAD LITTLE FRONT YARD HIS FRUSTRATED COLOR UNIQUE ABILITY WITH AND INDISPENSATE FOR TEACH OTHER STUDIES, ARE AWARDS BADGES, PUBLISHED BEFORE WELL AS A FIRE GROSS PLANS WERE ORIGINALLY CHARACTERS IN THE STRIP TO WHICH SEEM TO IT WHEN TEMPERED IN AND HALLOWING THEY'RE SIMPLY DRAWING IN GIVES ON" PRINCIPAL SPITTLE DISTORT, READERS COMICS ARE USE, WATTERSON TOOK TWO 16-MONTHS AFTER RESISTAKES A MORE CREAT DEAL TO CALVIN OFTEN HOBBES TO ADMITS "SLIMY, "BUT IT'S NAMED A NIGHT OUT SHE IS POINT OF NOT SEEN HOBBES THE BOOKS AT THAT I REMAINING BOOK HAMSTER HUEY ARE APPEARANCE: DECEMBER 6, 1995 MOM'S FRAMES OF CALVIN GIVEN A WAGON, SOMETIMES THAT SO IT'S FATHERE'S FAMILY NO CANCELLATIONSHIP WAS PRESENTS FROM NOVEMBER 21, 1985 LAST APPEAR ABSENCE IN ANOTHERWISE IT HAPPY TO RUN IT FOR THIS DAD AS "A LITTLE TO TOLERATE CALVIN'S FAMILY DRAWN ALMOST COMMENDED UP BEING PEOPLE INSTANCE, GET MARRIED BY A DANCE CALVIN'S OUTLANDISING THE NEWSPAPER OR TABLOID NEWSPAPER BUSINESS SHOW IS ON!" AND SPRINTS OF CHILDREN'S DAD'S FRUSTRATED BY TURN HUMOR, WAS PUBLIC DIALOG THERE'S NOT MUCH AS "'94 MODERNISM" WATTERSON HAS DELIGHTS OF FANTASY LIFE WATTERSON SAYS SERVES AS AN ARTISTS IS DESTRUCTION BUSINESS, SPACEFARER OF THE OPPORTUNITIES YOU BOTH A TOPIC FOR HIS HOME TONGUE-IN-CHEEK POPULAR THAT IT WAS "HON" AND QUARTER PAGE MORE SPACIOUS CANCELLATION THE PAIR ARE CLEARLY IN PSYCHIC TRANSMOGRIFIER'S "JAP" SOUND EFFECT YOU THINKER WATTERSON ALSO GREW INCREDIBLE SPACE BUYS IN COMMONLY WHILE OTHERWISE IT'S NAME IS NOTABLE STORYLINE GAVE THE OPPORTUNITIES YOU CANCELLATION THE "CALVIN OFFER TO MAKE HIM INCORRECT ANSWERS WATTER ARTWORK OTHER OFTEN WHICH IS EVIDENT TO OTHER STRIP IS TO THEIR USE OF RULES THAT SHOWN ON SANDIFER, WHO USES A CROWQUILL BE SEEN "GLUED" TO THE ONLY PERS AND HIS FATHER SUPPORT IS LUNCHLINE GAVE THESE THIN A YEAR IN MULTIMATERIAL AND OBTAIN ON SANTASY, HIS USE, WATTERS DIALOGUE IS AN "ARTIST'S STATUS AS "A DIM VIEW IN THE ESSENTIALLY TO MAKE HIM SEEM TO INCLUDED THAT CALVIN IS AN ODD DIALOGUE MOST OF THE CLUB HAS EXPRESSION OUTSIDE AVAILABLE TO
```
### Flag:
``` 
CTFlearn{IFONLYMODERNCRYPTOWASLIKETHIS}
```

## 5x5 Crypto 
### Given:
```
Ever heard of the 5x5 secret message system? If not, basically it's a 5x5 grid with all letters of the alphabet in order, without k because c is represented to make the k sound only. Google it if you need to. A letter is identified by Row-Column. All values are in caps. Try: 1-3,4-4,2-1,{,4-4,2-3,4-5,3-2,1-2,4-3,_,4-5,3-5,}
```
Using Google to search for a 5x5 decoder led me to reading about the Polybius Cipher which then led me to this site that I used to solve this challenge: https://www.dcode.fr/polybius-cipher 
The ciphertext is given to us as:
```
1-3, 4-4, 2-1, {,4-4, 2-3, 4-5, 3-2, 1-2, 4-3, _, 4-5, 3-5,}
```
And the encryption grid key can be built from the given statement, which lets us know to exclude K when filling out the grid. The following letters should be placed starting from the top and placing them left to right: ``` ABCDEFGHIJLMNOPQRSTUVWXYZ ```
#### Notice: The letter K is excluded in the encryption grid
After setting up, we can now use the decryption function on this site to get the flag output.
### Output:
``` 
CTFTHUMBSUP
```
### Flag:
``` 
CTFlearn{THUMBS_UP}
```

## RSA Noob
### Given:
```
These numbers were scratched out on a prison wall. Can you help me decode them? https://mega.nz/#!al8iDSYB!s5olEDK5zZmYdx1LZU8s4CmYqnynvU_aOUvdQojJPJQ
```
The link downloaded a file named ``` rsanoob (1).txt ```
### Output:
``` 
e: 1
c:9327565722767258308650643213344542404592011161659991421
n: 245841236512478852752909734912575581815967630033049838269083
```
After doing some research on the RSA encryption algorithm, I found the formula used in the encryption process:
```
(m^e) = c (mod n)
```

By substituion of the given variables from the ``` rsanoob (1).txt ``` file, we can solve for m:
```
(m^1) = 9327565722767258308650643213344542404592011161659991421 mod 245841236512478852752909734912575581815967630033049838269083
```
Using wolfram alpha to calculate, the result is:
```
9327565722767258308650643213344542404592011161659991421
```
Next, we can convert this decimal value into hexadeciaml and then into a string format to find the final flag output.
#### To hex:
```
61626374667B6233747465725F75705F793075725F657D
```
#### To ascii text:
```
abctf{b3tter_up_y0ur_e}
```
### Flag:
``` 
CTFlearn{b3tter_up_y0ur_e}
```

## ALEXCTF CR2: Many time secrets
### Given:
```
This time Fady learned from his old mistake and decided to use onetime pad as his encryption technique, but he never knew why people call it one time pad! Flag will start with ALEXCTF{.

https://mega.nz/#!DGxBjaDR!tMWkHf0s0svmkboGd-IASHsS9jACxSYx4zi_ETsyzyQ
```
The link downloaded a file named ``` msg (4) ```
### Output:
``` 

```
### Flag:
``` 

```