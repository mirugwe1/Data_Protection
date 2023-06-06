# AES AND RSA DATA ENCRYPTION ALGORITHM

 ## Contents

[Introduction](https://github.com/mirugwe1/Data_Protection#introduction)\
[AES Algorithm](https://github.com/mirugwe1/Data_Protection#aes-algorithm)\
[RSA Algorithm](https://github.com/mirugwe1/Data_Protection#rsa-algorithm)\
[Hybrid Encryption](https://github.com/mirugwe1/Data_Protection#hybrid-encryption)\
[Steps Involved](https://github.com/mirugwe1/Data_Protection#steps-involved)\
[Flow Diagram](https://github.com/mirugwe1/Data_Protection#flow-diagram)

## Introduction

This project implements the AES and RSA data encryption algorithms to provide secure transmission of confidential files. AES is a symmetric block cipher used for encrypting fixed-size blocks of plaintext, while RSA is an asymmetric encryption algorithm used for securely transmitting data over a communication channel.

## AES Algorithm

The Advanced Encryption Standard (AES) is a symmetric encryption algorithm that uses the same key for both encryption and decryption. It operates on fixed-size blocks of plaintext and produces ciphertext of the same size. AES supports key sizes of 128, 192, or 256 bits.

## RSA Algorithm

RSA (Rivest–Shamir–Adleman) is an asymmetric encryption algorithm that uses a public key for encryption and a private key for decryption. These keys are randomly generated using approved cryptography libraries. RSA is primarily suitable for small plaintext files due to its computational complexity.

## Hybrid Encryption

In this project, we employ a hybrid encryption scheme that combines the advantages of both AES and RSA algorithms. We use symmetric encryption (AES) to encrypt and decrypt the data and then employ RSA encryption to encrypt and decrypt the symmetric encryption key. This ensures secure distribution of the AES key and offers the benefits of fast encryption speed (AES) and easy management of RSA keys.

## Steps Involved

Sender:

* Obtain the file to encrypt.
* Generate a random AES symmetric key.
* Generate the recipient's public and private keys using approved cryptography libraries.
* Encrypt the AES key with the recipient's public key (RSA asymmetric encryption).
* Use the AES key to encrypt the file (AES symmetric encryption).
* Write both the encrypted file and the encrypted AES key to a bundled file.
* Send the bundled file to the recipient.

Recipient:

* Read the first 16 bytes of the bundled file (RSA encrypted AES key).
* Read the next 16 bytes and obtain the Initialization Vector (IV).
* Decrypt the AES key with the recipient's private RSA key.
* Use the decrypted AES key and IV to decrypt the rest of the bundled file.
* Open the decrypted file.

## Flow Diagram

![](https://github.com/mirugwe1/Data_Protection/blob/master/encryption.png)
