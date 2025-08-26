# RED picoCTF Write-Up

## Challenge Description
You are given an image file `red.png`. Your task is to analyze the image and extract the hidden flag.

## Solution Steps

- Use the `strings` command to inspect the image:
  ```
  strings red.png
  ```
  You will find a poem and hints like `CHECKLSB`.

- Use `zsteg` to analyze the image for hidden data in the least significant bits (LSB):
  ```
  zsteg red.png
  ```
  In the output, you will find a base64-encoded string in `b1,rgba,lsb,xy`:
  ```
  cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==
  ```

- Decode the base64 string to reveal the flag:
  ```
  echo "cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==" | base64 -d
  ```
  Output:
  ```
  picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}
  ```

## Flag
```
picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}
```