# HashingJobApp picoCTF Write-Up

## Challenge Description
In this challenge, we are given a remote service that asks us to compute MD5 hashes for given words. Our task is to provide the correct hash values to proceed and eventually obtain the flag.

## Solution Steps

1. **Connect to the Service**  
   We connect to the given address using `nc` (netcat):
   ```bash
   nc saturn.picoctf.net 57205
   ```
   The service prompts us with a request to compute an MD5 hash for a given word.

2. **Compute MD5 Hash**  
   We take the given word, compute its MD5 hash, and input the result. Since different words may be provided in each attempt, we can use an online MD5 generator such as [MD5 Hash Generator](https://www.md5hashgenerator.com/) to quickly compute the required hashes.

   Example:
   - Given: `'Atlantis'`
     - MD5 hash: `a425a3c39e1eaba4a378b0a08d80db9b`
   - Given: `'mold'`
     - MD5 hash: `0ad9f975892bdc82aa683146c002ffac`
   - Given: `'Japan'`
     - MD5 hash: `53a577bb3bc587b0c28ab808390f1c9b`

   Since the words may vary, simply take the given word and generate the MD5 hash using the provided online tool.

3. **Receive the Flag**  
   After successfully computing and submitting the correct MD5 hashes, the service provides the final flag:
   ```
   picoCTF{4ppl1c4710n_r3c31v3d_bf2ceb02}
   ```

## Flag
```
picoCTF{4ppl1c4710n_r3c31v3d_bf2ceb02}
```