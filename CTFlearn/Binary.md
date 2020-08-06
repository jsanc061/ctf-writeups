Binary

## Lazy Game Challenge
### Given:
```
I found an interesting game made by some guy named "John_123". It is some betting game. I made some small fixes to the game; see if you can still pwn this and steal $1000000 from me!

To get flag, pwn the server at: nc thekidofarcrania.com 10001

```
### Output:
``` 
Welcome to the Game of Luck !.

Rules of the Game :
(1) You will be Given 500$
(2) Place a Bet
(3) Guess the number what computer thinks of !
(4) computer's number changes every new time !.
(5) You have to guess a number between 1-10
(6) You have only 10 tries !.
(7) If you guess a number > 10, it still counts as a Try !
(8) Put your mind, Win the game !..
(9) If you guess within the number of tries, you win money !
(10) Good Luck !..

theKidOfArcrania:
  I bet you cannot get past $1000000!

Are you ready? Y/N :
```

I was able to enter large, negative bet (-$10000000000000000000) towards the game and kept guessing values outside of 1-10 to break more of the game's rules. At the end of the 10 rounds, it said I lost the game, but then update my currency to $10000000000000000500 which prompted the flag to display
### Flag:
``` 
CTFlearn{d9029a08c55b936cbc9a30_i_wish_real_betting_games_were_like_this!}
```


