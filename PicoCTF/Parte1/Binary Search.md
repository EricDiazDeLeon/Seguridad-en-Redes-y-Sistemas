## Objetivo 
Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics.
## Solución  
```bash
ericdiaz-picoctf@webshell:~$ ssh -p 57896 ctf-player@atlas.picoctf.net
The authenticity of host '[atlas.picoctf.net]:57896 ([18.217.83.136]:57896)' can't be established.
ED25519 key fingerprint is SHA256:M8hXanE8l/Yzfs8iuxNsuFL4vCzCKEIlM/3hpO13tfQ.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[atlas.picoctf.net]:57896' (ED25519) to the list of known hosts.
ctf-player@atlas.picoctf.net's password: 
Welcome to the Binary Search Game!
I'm thinking of a number between 1 and 1000.
Enter your guess: 500
Higher! Try again.
Enter your guess: 560
Higher! Try again.
Enter your guess: 800
Lower! Try again.
Enter your guess: 630
Lower! Try again.
Enter your guess: 611
Lower! Try again.
Enter your guess: 569
Higher! Try again.
Enter your guess: 575
Lower! Try again.
Enter your guess: 573
Lower! Try again.
Enter your guess: 572
Congratulations! You guessed the correct number: 572
Here's your flag: picoCTF{g00d_gu355_de9570b0}
Connection to atlas.picoctf.net closed.

```

## Notas Adicionales 

### Referencias