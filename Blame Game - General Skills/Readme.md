# Blame Game picoCTF Write-Up

## Challenge Description
You are given a zip file containing a project with a `.git` directory. Your goal is to investigate the git history to find the flag.

## Solution Steps

- Extract `challenge.zip` and navigate to the extracted folder. You will see:
  ```
  .git  message.py
  ```
- Use `git log -p -- message.py` to view the commit history and changes:
  ```
  git log -p -- message.py
  ```
- In the commit history, look for unusual author names or commit messages.  
  The first commit shows:
  ```
  Author: picoCTF{@sk_th3_1nt3rn_ea346835} <ops@picoctf.com>
  ```
- The flag is embedded in the author field of the commit:
  ```
  picoCTF{@sk_th3_1nt3rn_ea346835}
  ```

## Flag
```
picoCTF{@sk_th3_1nt3rn_ea346835}
```