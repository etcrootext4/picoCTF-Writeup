# Ph4nt0m 1ntrud3r picoCTF Write-Up

## Challenge Description
You are given a `.pcap` file and need to analyze the network traffic to find the hidden flag.

## Solution Steps

- Open the `.pcap` file using Wireshark or a similar tool.
- Search for traffic containing base64-encoded strings, such as `cGljb0NURg==`.
- Filter TCP packets with the string `==` to find all relevant base64 fragments.
- Collect and order the fragments by timestamp:
  ```
  cGljb0NURg==
  ezF0X3c0cw==
  bnRfdGg0dA==
  XzM0c3lfdA==
  YmhfNHJfMg==
  ZTFmZjA2Mw==
  fQ==
  ```
- Concatenate all fragments into one string:
  ```
  cGljb0NURg==ezF0X3c0cw==bnRfdGg0dA==XzM0c3lfdA==YmhfNHJfMg==ZTFmZjA2Mw==fQ==
  ```
- Decode the concatenated string with base64:
  ```
  echo "cGljb0NURg==ezF0X3c0cw==bnRfdGg0dA==XzM0c3lfdA==YmhfNHJfMg==ZTFmZjA2Mw==fQ==" | base64 -d
  ```
  Output:
  ```
  picoCTF{1t_w4snt_th4t_34sy_tbh_4r_2e1ff063}
  ```

## Flag
```
picoCTF{1t_w4snt_th4t_34sy_tbh_4r_2e1ff063}
```