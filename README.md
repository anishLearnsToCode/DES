# 🗝 DES (Data Encryption Standard)

![made-with-python](https://img.shields.io/badge/Made%20with-Python%203-1f425f.svg)

## Introduction
The __Data Encryption Standard (DES)__ is a symmetric-key block cipher published by the __National Institute of 
Standards and Technology (NIST)__. Here, DES has been implemented in Python 3 with no other dependencies. A full 
explanation of the cipher along with the Code can be seen in this
[Jupyter Notebook](notebook/data-encryption-standard-des.ipynb).

The DES structure uses many smaller Ciphers such as the single Round Fiestel Cipher, which in turn uses the
single Swapper and Mixer Ciphers. All of these smaller constructs have lso been built in individual classes and these
smaller constructs have been composed together to form the DES Algorithm.   

These smaller Ciphers can also be used individual or composed together to create different Ciphers. These building 
blocks are:

- [P-Boxes (Permutation Boxes)](des/PBox.py)
- [S-Boxes (Substitution Boxes)](des/SBox.py)
- [Swapper Cipher](des/Swapper.py)
- [Mixer Cipher](des/Mixer.py)
- [Single Round Fiestel Cipher](des/Round.py)
- [DES (Data Encryption Standard)](des/DES.py)

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

### 1. `.encrypt(binary: str) -> str`
This method takes in a binary string with 64 bits and will return a binary encrypted string with
64 bits.

```python
from des import DES
from des.utils import *

des = DES(key=13)
ciphertext = des.encrypt(int_to_bin(12345, block_size=64))
decrypted_binary = des.decrypt(ciphertext)
print('Decrypted:', int(decrypted_binary, base=2))
``` 

### 2. `.encrypt_number(number: int) -> int`
This takes in a 4 Byte unsigned number and returns a 64 bit unsigned encrypted value.

```python
from des import DES
from des.utils import *

des = DES(key=13)
ciphertext = des.encrypt_number(12345)
decrypted = des.decrypt_number(ciphertext)
print('Decrypted:', decrypted)
```

### 3. `.encrypt_message(message: str) -> list[int]`
This method takes in a string (character sequence) and returns a list of integers where every 
integer in the list is an encrypted 64 bit unsigned version of every character in the message
string.

```python
from des import DES
from des.utils import *

des = DES(key=13)
ciphertext = des.encrypt_message('hello world 👋')
decrypted = des.decrypt_message(ciphertext)
print('Decrypted:', decrypted)
```

## References
1. [Data Encryption Standard ~ Wikipedia](https://en.wikipedia.org/wiki/Data_Encryption_Standard)
1. [Data Encryption Standard ~ TutorialsPoint](https://www.tutorialspoint.com/cryptography/data_encryption_standard.htm)
1. [Cryptography and Network Security ~ Behrouz A. Forouzan](https://books.google.co.in/books?id=OYiwCgAAQBAJ)
