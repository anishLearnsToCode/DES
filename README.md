# 🗝 DES (Data Encryption Standard)

## Introduction

## Running it Locally
Clone this repository on your machine and enter directory. 
```powershell
git clone https://github.com/anishLearnsToCode/DES.git
cd DES
```
Run the `driver.py` program to see the output of a number being encrypted and decrypted using
DES.

```powershell
python driver.py
```

```shell script
Number: 123456
Encrypted: 7349708071395271833
Decrypyed 123456
```

The DES algorithm also offers more API endpoints.

## Using the API

### `.encrypt(binary: str) -> str`
This method takes in a binary string with 64 bits and will return a binary encrypted string with
64 bits.

```python
from des import DES
from des.utils import *

des = DES(key=13)
ciphertext = des.encrypt(int_to_bin(12345, block_size=64))
print(des.decrypt(ciphertext))
``` 

## References
1. [Data Encryption Standard ~ Wikipedia](https://en.wikipedia.org/wiki/Data_Encryption_Standard)
1. [Data Encryption Standard ~ TutorialsPoint](https://www.tutorialspoint.com/cryptography/data_encryption_standard.htm)
1. [Cryptography and Network Security ~ Behrouz A. Forouzan](https://books.google.co.in/books?id=OYiwCgAAQBAJ)
