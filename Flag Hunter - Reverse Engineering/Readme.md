# Flag Hunters picoCTF Write-Up

## Challenge Description
Lyrics jump from verses to the refrain kind of like a subroutine call. There's a hidden refrain this program doesn't print by default. Can you get it to print it? There might be something in it for you.

## Solution Steps

- The flag is stored in `flag.txt` and inserted at the beginning of the song string (`secret_intro`).
- The program plays the song line by line, starting from a specific label.
- Special commands in the song:
  - `REFRAIN` jumps to the refrain section.
  - `RETURN <number>` jumps to a specific line.
  - `CROWD ...` asks for user input.

**Key Exploit:**
- When prompted for `Crowd:`, any input is stored as a new song line prefixed with `Crowd: `.
- If you input `RETURN 0`, it becomes `Crowd: RETURN 0` and won't match the jump regex.
- However, the program splits input by `;`, so if you input `;RETURN 0`, it creates a new line `RETURN 0` without the prefix.
- This matches the regex and jumps to line 0, printing the secret intro with the flag.

**Steps:**
1. Run the challenge:
   ```
   nc <host> <port>
   ```
2. When prompted for `Crowd:`, input:
   ```
   ;RETURN 0
   ```
3. The program jumps to line 0 and prints the flag.

## Flag
```
picoCTF{70637h3r_f0r3v3r_62666df2}
```