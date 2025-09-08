# Binary Search picoCTF Write-Up

## Challenge Description
Want to play a game? As you use more of the shell, you might be interested in how they work! Binary search is a classic algorithm used to quickly find an item in a sorted list. Can you find the flag? You'll have 1000 possibilities and only 10 guesses.

Cyber security often has a huge amount of data to look through - from logs, vulnerability reports, and forensics. Practicing the fundamentals manually might help you in the future when you have to write your own tools!

## Solution Steps

- Connect to the challenge server using SSH:
  ```
  ssh -p 64791 ctf-player@atlas.picoctf.net
  ```
- The game will ask you to guess a number between 1 and 1000. You have 10 guesses.
- Use the binary search algorithm:
  - Start with the middle value (500).
  - If the response is "Higher!", guess the midpoint between your last guess and the upper bound.
  - If the response is "Lower!", guess the midpoint between your last guess and the lower bound.
  - Continue narrowing the range based on the feedback until you find the correct number.
- Example session:
  ```
  Enter your guess: 500
  Higher! Try again.
  Enter your guess: 750
  Lower! Try again.
  Enter your guess: 625
  Higher! Try again.
  Enter your guess: 690
  Lower! Try again.
  Enter your guess: 660
  Higher! Try again.
  Enter your guess: 675
  Higher! Try again.
  Enter your guess: 683
  Lower! Try again.
  Enter your guess: 678
  Higher! Try again.
  Enter your guess: 680
  Congratulations! You guessed the correct number: 680
  Here's your flag: picoCTF{g00d_gu355_2e90d29b}
  ```

## Flag
```
picoCTF{g00d_gu355_2e90d29b}
```