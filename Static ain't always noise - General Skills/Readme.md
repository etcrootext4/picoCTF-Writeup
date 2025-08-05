# Static ain't always noise picoCTF Write-Up

## Description
This challenge involves analyzing a binary file named `static`. The task is to extract the hidden flag by disassembling the binary and examining its strings.

## Steps to Solve

1. **List Directory Contents**  
   Start by listing the available files in the working directory:
   ```bash
   ls
   ```
   Output:
   ```
   README.txt  ltdis.sh  static
   ```

2. **Grant Execution Permission**  
   The script `ltdis.sh` is provided for disassembling the binary. First, give it execution permissions:
   ```bash
   chmod +x ltdis.sh
   ```

3. **Run the Disassembly Script**  
   Initially, running the script without arguments will fail:
   ```bash
   ./ltdis.sh
   ```
   Output:
   ```
   Attempting disassembly of  ...
   objdump: 'a.out': No such file
   Disassembly failed!
   Usage: ltdis.sh <program-file>
   Bye!
   ```

   To correctly run it:
   ```bash
   ./ltdis.sh static
   ```
   Output:
   ```
   Attempting disassembly of static ...
   Disassembly successful! Available at: static.ltdis.x86_64.txt
   Ripping strings from binary with file offsets...
   Any strings found in static have been written to static.ltdis.strings.txt with file offset
   ```

4. **Check Generated Files**  
   After disassembly, list the directory contents:
   ```bash
   ls
   ```
   Output:
   ```
   README.txt  ltdis.sh  static  static.ltdis.strings.txt  static.ltdis.x86_64.txt
   ```

5. **Analyze Strings for the Flag**  
   Inspect the `static.ltdis.strings.txt` file:
   ```bash
   cat static.ltdis.strings.txt
   ```
   Among the output, the following line contains the flag:
   ```
   1020 picoCTF{d15a5m_t34s3r_ae0b3ef2}
   ```

## Flag
```
picoCTF{d15a5m_t34s3r_ae0b3ef2}
```

