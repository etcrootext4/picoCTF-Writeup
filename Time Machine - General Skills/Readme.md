# Time Machine picoCTF Write-Up

## Challenge Description
What was I last working on? I remember writing a note to help me remember.

## Solution Steps

- Extract the provided `challenge.zip` file.
- Inside the extracted `drop-in` directory, you will find a `.git` folder and `message.txt`.
- The `message.txt` file suggests checking the commit history.
- Use the following command to view the git commit log:
  ```
  git log -p
  ```
- The flag is found in the commit message:
  ```
  picoCTF{t1m3m@ch1n3_186cd7d7}
  ```

## Flag
```
picoCTF{t1m3m@ch1n3_186cd7d7}
```