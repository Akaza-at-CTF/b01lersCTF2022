# crackme

> Security through obscurity is no match for you!

Disassemble the file using `objdump -d crackme > crackme.asm`.  The file uses a check function to compare an input string with the passphrase hidden in the code. Looking at the check function, it checks each character of the input string with hardcoded ASCII values using `cmp`. Use `grep cmp crackme.asm` to show all `cmp` instances and covert the ASCII values to get the flag.

![grepcrackme](https://github.com/N-2-O/b01lersCTF2022/blob/main/rev/crackme/grepcrackme.asm.png)

The flag is `bctf{133&_letmein_123}`.
