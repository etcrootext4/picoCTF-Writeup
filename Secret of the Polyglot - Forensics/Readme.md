# Secret of the Polyglot picoCTF Write-Up

## Challenge Description
This challenge involves analyzing a file that appears to be a PDF but contains hidden data. The hint suggests opening the file in a different way, leading to the discovery of an embedded image. The goal is to extract the complete flag from the file.

## Solution Steps

1. **Analyze the Provided File**  
   Upon opening the given PDF file in a standard viewer, we see the text:
   ```
   1n_pn9_&_pdf_2a6a1ea8}
   ```
   This suggests that it might be a part of the flag.

2. **Examine the File Using a Text Editor**  
   Following the hint, we open the file in Notepad (or any text editor). At the beginning of the file, we notice the presence of the string `PNG`, which indicates that the file might actually be an image in PNG format.

3. **Change the File Extension**  
   Given the `PNG` signature in the file, we rename the file extension from `.pdf` to `.png` and open it using an image viewer.

4. **Extract the Flag from the Image**  
   The image contains the text:
   ```
   picoCTF{f1u3n7_
   ```
   When combined with the previously discovered text, the complete flag is:
   ```
   picoCTF{f1u3n7_1n_pn9_&_pdf_2a6a1ea8}
   ```

## Flag
```
picoCTF{f1u3n7_1n_pn9_&_pdf_2a6a1ea8}
```