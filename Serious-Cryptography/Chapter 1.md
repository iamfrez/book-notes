# Notes on Chapter 1: Encryption



Encryption ensure data's *confidentiality*. It uses an algorithm called a *cipher* and a secret value called a *key*. 



In *symmetric encryption*, the key used to decrypt is the same as the key used to encrypt. 



*plaintext*: unencrypted message.

*ciphertext*: encrypted message.



![1552257849940](./images/1552257849940.png)

A cipher, **E**, takes a plaintext **P** and a key **K** as input, producing a ciphertext **C** as output.



> Ciphertexts can never be shorter than plaintexts.



The **Caesar Cipher** encrypts a message by shifting each of the letters down three positions in the alphabet, wrapping back around to A if the shift reaches Z. 

This cipher is very easy to break. 



The **Vigenere Cipher**, created in the 16th century, is very similar to the Caesar cipher, except that letters aren't shifted by three places but rather by values defined by a *key*, a collection of letters that represent numbers based on their position in the alphabet. For example, if the key is DUH, letters in the plaintext are shifted using the values 3, 20, 7 because D is three letters after A, U is 20, and H is 7.

This cipher can be broken using a method called *frequency analysis*, which exploits the uneven distribution of letters in languages.



Auguste Kerckhoffs



A cipher has two main components: a permutation and a mode of operation. A *permutation* is a function that transforms an item (in cryptography, a letter or a group of bits) such that each item has a unique inverse. A *mode of operation* is an algorithm that uses a permutation to process messages of arbitrary size.



The representation or encoding of information is a separate matter that is mostly irrelevant to security. 



A cipher's substitution can't be just any substitution. It should be a permutation, which is a rearrangement of the letters *A* to *Z*, such that each letter has a unique inverse. [...] With a permutation, each letter has exactly one inverse.

A permutation, in order to be secure, needs to satisfy:

- **Permutation should be determined by the key**, to keep the permutation secret as long as the key is secret.
- **Different keys should result in different permutations**. 
- **The permutation should look random**. 

We'll call a permutation that satisfies these criteria as a *secure permutation*. However, a secure permutation is *necessary but not sufficient* on its own for building a secure cipher.