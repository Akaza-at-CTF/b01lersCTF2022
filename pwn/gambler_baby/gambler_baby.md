# gambler_baby

> Feeling lucky? 
> 
> You must create a flag.txt in the same folder as the binary for it to run.
> 
> nc ctf.b01lers.com 9202


The goal is to correctly guess the word until we get 1000 coins, when the program will give the flag. The words are not random and the wordlist is fixed. Arbitrarily guess words and the program will show you the correct word. Put the correct words in a file named `guess`, you will need 90 words. Play the game using `nc ctf b01lers.com 9202 < guess` but the connection cuts off prematurely. Instead, write python script with pwntools:

```python
from pwn import *

conn = remote("ctf.b01lers.com", 9202)
print(conn.recv())
f = open("guess", "r")
for guess in f:
        print(conn.send(guess))
        print(conn.recv())
        
f.close()
conn.close()
```

The flag is `bctf{n0_pr4153_f0r_RNGesus}`.

