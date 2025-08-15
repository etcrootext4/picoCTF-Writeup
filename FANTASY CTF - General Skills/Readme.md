# FANTASY CTF picoCTF Write-Up

## Challenge Description
Play this short game to get familiar with terminal applications and some of the most important rules in scope for picoCTF.

## Solution Steps

- Connect to the challenge server using netcat:
  ```
  nc verbal-sleep.picoctf.net 55716
  ```
- Follow the interactive story and answer the prompts correctly:
  - Choose to register a single, private account (`c`).
  - Choose to play the game (`a`).
- Complete the game simulation and find the flag at the end.

## Flag
```
picoCTF{m1113n1um_3d1710n_fc649bc5}
```