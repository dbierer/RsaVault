# RsaVault
Implements a box-algorithm for RSA public/private key pairs

## Vault Architecture
Imagine a box of logs.  Each log is uniform in length.  In each box is stacked 27 logs in a 3 x 3 x 3 arrangement.  
Each "log" represents a different key.  This is the structure of each "vault".  Depending on processing power, 
this arrangement could be expanded to 9 x 9 x 9 and on up depending on the security level required.

## Public Key Vault (PubKV)
This is a vault which is generated and stored on the server side.  Each "log" represents an RSA public key.

## Private Key Vault
Each log represents a private key generated against a matching public key vault log.

## Encryption Options
* Message Log Length (MLL)
  * how many bytes of the message to encrypt before switching to the next key
* Cycling Algorithm
  * mathematical algorithm which will sweep through the PubKV setting a cluster of public keys to use 
    for the encryption.  Algorithms chosen are 3D and based on basic shapes such as an ellipse, a
    circle, and oval, etc.

## Encryption Process
* Using the Cycling Algorithm, set which keys in the Public Key Vault will be used in the encryption
* Loop through the public keys, encrypting MLL bytes at a time


 
