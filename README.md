**AES Project - Encryption and Decryption**
Introduction to AES
AES (Advanced Encryption Standard) is a widely used symmetric encryption algorithm for securing data. It uses a fixed-size key for both encryption and decryption. AES supports key sizes of 128, 192, or 256 bits. This project implements AES-128, meaning it uses a 128-bit key for encrypting and decrypting data.

AES works in 10 rounds for AES-128. Each round involves several transformations applied to the data block:

SubBytes: Each byte of the data block is replaced with another byte from a substitution table.
ShiftRows: The rows of the data block are shifted in a circular fashion.
MixColumns: The columns of the data block are mixed to spread the information.
AddRoundKey: The round key is added to the data block using XOR.
The final round omits the MixColumns step.

**How the Code Works**
This project implements both AES encryption and decryption for AES-128.

**Encryption**
Encryption consists of 10 rounds of transformations. Here are the steps followed in each round:

AddRoundKey: The round key is XORed with the data block.
SubBytes: Each byte is replaced with a byte from the substitution table.
ShiftRows: The rows of the data block are shifted.
MixColumns: The columns are mixed to spread the bits.
The last round omits MixColumns.

**Decryption**
Decryption follows the reverse order of encryption steps but with inverse operations:

AddRoundKey: The round key is XORed with the data block.
InverseShiftRows: The rows are shifted in the opposite direction.
InverseSubBytes: The bytes are replaced by their inverse values from the substitution table.
InverseMixColumns: The columns are reversed to undo the effect of MixColumns.
The final round of decryption does not include InverseMixColumns, as it is not used in the last round of encryption.

**Code Functionality**
Encryption works correctly for all rounds and generates valid ciphertext.
Decryption works partially. The decryption process is in place, but some parts of the algorithm, like InverseMixColumns, are not yet fully implemented, which prevents perfect decryption in all cases.
Current Limitations
Decryption is not fully functional yet. The InverseMixColumns step is not correctly implemented, preventing accurate recovery of the plaintext.
