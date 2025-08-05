# Glitch Cat picoCTF Write-Up

## Challenge Description
In this challenge, we are given an encoded flag where part of it is represented using `chr()` function calls with hexadecimal values. Our task is to decode these ASCII values and reconstruct the flag.

## Solution Steps

1. **Connect to the Service**  
   We use `nc` (netcat) to connect to the provided service:
   ```bash
   nc saturn.picoctf.net 57132
   ```
   The service returns the following encoded flag:
   ```python
   'picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}'
   ```

2. **Decode the ASCII Characters**  
   The given `chr()` function calls represent ASCII characters in hexadecimal format. To decode them, we use Python:
   ```bash
   python3 -c "print('picoCTF{gl17ch_m3_n07_' + chr(0x62) + chr(0x64) + chr(0x61) + chr(0x36) + chr(0x38) + chr(0x66) + chr(0x37) + chr(0x35) + '}')"
   ```
   This command outputs:
   ```
   picoCTF{gl17ch_m3_n07_bda68f75}
   ```

3. **Submit the Flag**  
   After decoding, we obtain the complete flag:
   ```
   picoCTF{gl17ch_m3_n07_bda68f75}
   ```

## Flag
```
picoCTF{gl17ch_m3_n07_bda68f75}
```
