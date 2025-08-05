# Nice Netcat picoCTF Write-up

## **Challenge Description**
In this challenge, we are given a network service running on a specific host and port. The goal is to connect to it using `netcat` (nc) and retrieve the hidden flag. The challenge also requires decoding ASCII values into a readable flag.

---

## **Tools Used**
- **Netcat (`nc`)**: For establishing a TCP connection to the provided server.
- **Python (`chr()` function)**: To convert ASCII codes to a readable string (the flag).

---

## **Step-by-Step Solution**

### **Step 1: Connect to the Server with Netcat**
Use `nc` to connect to the given server (`mercury.picoctf.net`) and port (`22902`):

```bash
nc mercury.picoctf.net 22902
```

### **Step 2: Retrieve the ASCII Codes**
Upon connecting, the server responds with a sequence of ASCII values:

```
112
105
99
111
67
84
70
123
103
48
48
100
95
107
49
116
116
121
33
95
110
49
99
51
95
107
49
116
116
121
33
95
100
51
100
102
100
54
100
102
125
```

---

### **Step 3: Convert ASCII Codes to Text Using Python**
The received numbers represent ASCII codes. We can decode them using Python's `chr()` function:

```bash
python3 -c "print(''.join([chr(x) for x in [112,105,99,111,67,84,70,123,103,48,48,100,95,107,49,116,116,121,33,95,110,49,99,51,95,107,49,116,116,121,33,95,100,51,100,102,100,54,100,102,125]]))"
```

### **Step 4: Final Output**
After running the Python command, we get the final flag:

```
picoCTF{g00d_k1tty!_n1c3_k1tty!_d3dfd6df}
```

---

## **Flag**
```
picoCTF{g00d_k1tty!_n1c3_k1tty!_d3dfd6df}
```