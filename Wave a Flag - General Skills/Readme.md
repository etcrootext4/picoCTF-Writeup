# Wave a Flag picoCTF Write-Up

## Challenge Description
This challenge involves executing a binary file named `warm`. The binary contains a hidden flag that can be revealed by providing the correct parameter during execution.

## Solution Steps

1. **Downloading the File**  
   Begin by downloading the `warm` file from the provided URL using:
   ```bash
   wget https://mercury.picoctf.net/static/cfea736820f329083dab9558c3932ada/warm
   ```

2. **Verifying the Download**  
   Check that the file has been successfully downloaded by listing the contents of the directory:
   ```bash
   ls
   ```

3. **Granting Execution Permission**  
   Since the file lacks execution permissions, add them using:
   ```bash
   chmod +x warm
   ```

4. **Running the Binary**  
   Execute the file with:
   ```bash
   ./warm
   ```
   The output will be:
   ```
   Hello user! Pass me a -h to learn what I can do!
   ```
   This suggests that a `-h` parameter may provide further information.

5. **Using the -h Parameter**  
   Run the binary with the `-h` option to check for the hidden flag:
   ```bash
   ./warm -h
   ```
   Output:
   ```
   Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_30e77291}
   ```

## Flag
```
picoCTF{b1scu1ts_4nd_gr4vy_30e77291}
```