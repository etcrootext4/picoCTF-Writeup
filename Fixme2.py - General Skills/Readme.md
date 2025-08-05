# Fixme2.py picoCTF Write-Up

## Challenge Description
The challenge provides a Python script named `fixme2.py` that contains an error preventing it from running correctly. The goal is to identify and correct the issue so that the script executes successfully and reveals the flag.

## Solution Steps

1. **Download the Script**  
   Using `wget`, we download the script from the provided URL:
   ```bash
   wget https://artifacts.picoctf.net/c/4/fixme2.py
   ```
   After downloading, we check that the file exists:
   ```bash
   ls
   ```
   The file `fixme2.py` should now be in our working directory.

2. **Run the Script and Observe the Error**  
   Attempting to run the script results in the following syntax error:
   ```bash
   python fixme2.py
   ```
   Output:
   ```
     File "/home/Art1cx-picoctf/fixme2.py", line 22
       if flag = "":
          ^^^^^^^^^
   SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
   ```
   
   The error message indicates an issue with the `if` statement. Specifically, `=` is used for assignment, whereas `==` is required for comparison.

3. **Fix the Syntax Error**  
   Open `fixme2.py` in a text editor, such as `nano`:
   ```bash
   nano fixme2.py
   ```
   Locate line 22 and change:
   ```python
   if flag = "":
   ```
   to:
   ```python
   if flag == "":
   ```
   Save the file and exit the editor.

4. **Run the Fixed Script**  
   Execute the corrected script:
   ```bash
   python fixme2.py
   ```
   Output:
   ```
   That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_e8814d03}
   ```

## Flag
```
picoCTF{3qu4l1ty_n0t_4551gnm3nt_e8814d03}
```

