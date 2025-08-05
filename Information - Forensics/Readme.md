# Information picoCTF Write-Up

## Challenge Description
This challenge involves analyzing an image file (`cat.jpg`) to extract hidden information. The goal is to inspect the metadata of the file to uncover the flag.

## Solution Steps

1. **Download the Image File**  
   First, we download the given file using `wget`:
   ```bash
   wget https://mercury.picoctf.net/static/e5825f58ef798fdd1af3f6013592a971/cat.jpg
   ```
   The file is successfully saved as `cat.jpg`.

2. **Check the File List**  
   We verify the downloaded file exists by listing the directory contents:
   ```bash
   ls
   ```
   Output:
   ```
   README.txt  cat.jpg  code.py  codebook.txt
   ```

3. **Extract Metadata Using ExifTool**  
   Using `exiftool`, we inspect the metadata of `cat.jpg`:
   ```bash
   exiftool cat.jpg
   ```
   From the output, we notice an interesting field:
   ```
   License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
   ```

4. **Decode the Base64 String**  
   The `License` field contains a Base64-encoded string. We decode it using:
   ```bash
   echo "cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9" | base64 -d
   ```
   Output:
   ```
   picoCTF{the_m3tadata_1s_modified}
   ```

## Flag
```
picoCTF{the_m3tadata_1s_modified}
```