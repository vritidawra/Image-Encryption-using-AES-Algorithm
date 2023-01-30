# Image-Encryption-using-AES-Algorithm
Introduction
The primary objective of image encryption is to transmit an image securely over a connected network so that no unauthorized user should be able to decrypt the image. Image encryption has applications in many fields including Banking, Telecommunication and Medical Image Processing etc. Encryption has become an important part due to the emergence of Internet, where sending and receiving data across computers need security of some standard. Various algorithms have been proposed in this field to encrypt and decrypt images.
An encryption scheme has been proposed that splits the Image into R, G, and B components and encrypt them using AES.
Image processing is a mechanism in which an original image will be converted into digital image and after converting in
digital form processes it to get useful information. It is a type of signal processing in which input is an image and output may be
image or characteristics/features associated with that image. In recent years, the advances in communication technology have
seen strong interest in digital image transmission. However, growth of computer processor possessing power and storage
illegal access has become easier. Encryption involves applying special mathematical algorithms and keys to transform digital
data into cipher code before they are transmitted and decryption involves the application of mathematical algorithms and keys to
get back the original data from cipher code, scientific community have seen strong interest in image transmission. Information
privacy becomes a challenging issue. In order to protect valuable data or image from undesirable readers, data or image encryption
/ Decryption is essential, furthermore. As such in this paper, a scheme based on encryption has been proposed for secure image
transmission over channels.


AES algorithm
AES is a 128-bit symmetric block ciphertext. This algorithm uses substitution and permutations. It consists of multiple texts to produce a ciphertext. AES performs its calculations in the form of byte data instead of bit data.
AES treats 128 bits of a clear text block as 16 bytes. The number of rounds during the encryption process depends on the key size being used. For example:
•	The 128-bit key size uses 10 rounds.
•	The 192-bit key size uses 12 rounds.
•	The 256-bit key size uses 14 rounds. 





Encryption Process
The encryption phase of AES can be broken into three phases:
the initial round, the main rounds, and the final round.
1. Initial Round
•	AddRoundKey
2. Main Rounds
•	SubBytes
•	ShiftRows
•	MixColumns
•	AddRoundKey
3. Final Round
•	SubBytes
•	ShiftRows
•	AddRoundKey

 



 

Creation of Round keys:
A Key Schedule algorithm is used to calculate all the round keys
from the key. So, the initial key is used to create many different
round keys which will be used in the corresponding round of the
encryption.

Byte Substitution (SubBytes)
The 16 input bytes are substituted by looking up a fixed table
(S-box) given in design. The result is in a matrix of four rows
and four columns. This step implements the substitution. In this
step each byte is substituted by another byte. (It performed using
a lookup table also called the S-box. This substitution is done in a
way that a byte is never substituted by itself and also not
substituted by another byte which is a compliment of the current
byte. The result of this step is a 16-byte (4 x 4) matrix like
before. The next two steps implement the permutation.


Shiftrows
Each of the four rows of the matrix is shifted to the left. Any
entries that ‘fall off’ are re-inserted on the right side of row.
●First row is not shifted.
●Second row is shifted one (byte) position to the left.
●Third row is shifted two positions to the left.
●Fourth row is shifted three positions to the left.
The result is a new matrix consisting of the same 16 bytes but
shifted with respect to each other.

 



MixColumns
Each column of four bytes is now transformed using a special
mathematical function. This function takes as input the four
bytes of one column and outputs four completely new bytes,
which replace the original column. The result is another new
matrix consisting of 16 new bytes. It should be noted that this
step is not performed in the last round.
(This multiplication has the property of operating independently over each of the
columns of the initial matrix, i.e. the first column when multiplied by the matrix,
produces the first column of the resultant matrix.)
 

Addroundkey
The 16 bytes of the matrix are now considered as 128 bits and
are XORed to the 128 bits of the round key. If this is the last
round then the output is the ciphertext. Otherwise, the resulting
128 bits are interpreted as 16 bytes and we begin another similar
round.



Decryption Process 

The process of decryption of an AES ciphertext is similar to the
encryption process in the reverse order. Each round consists of
the four processes conducted in the reverse order −
1. Inverse Final Round
•	AddRoundKey
•	ShiftRows
•	SubBytes
2. Inverse Main Round
•	AddRoundKey
•	MixColumns -This step is similar to the MixColumns step in encryption, but differs in the matrix used to carry out the operation.
•	ShiftRows
•	SubBytes -Inverse S-box is used as a lookup table and using which the bytes are substituted during decryption.
3. Inverse Initial Round
•	AddRoundKey
Since sub-processes in each round are in reverse manner, unlike
for a Feistel Cipher, the encryption and decryption algorithms
needs to be separately implemented, although they are very
closely related.
Of the four operations in AES encryption, only the
AddRoundKey operation is its own inverse (since it is an
exclusive-or).
To undo AddRoundKey, it is only necessary to expand the entire
AES key schedule (identically to encryption) and then use the
appropriate key in the exclusive-or. The other three operations
require an inverse operation to be defined and used.
The first operation to be undone is ShiftRows. The Inverse
ShiftRows operation is identical to the ShiftRows operation
except that rotations are made to the right instead of to the left.
The next operation to be undone is the SubBytes operation. The
Inverse S-Box is used which is read identically to the S-Box
matrix.
The last inverse operation to define is MixColumns. Like
MixColumns, Inverse MixColumns can be defined as the matrix
multiplication.


