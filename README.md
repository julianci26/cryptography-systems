# Cryptography
---
## Table of Contents:
1. Introduction
     2. Historical Cryptography
     3. Substitution Ciphers
     4. Poly-alphabetic Substitution Ciphers
     5. Transposition Ciphers
6. Goals of Cryptography
     7. Confidentiality
     8. Integrity
     9. Authentication
     10. Non-reputation
11. Cryptographic Concepts
     12. Cryptographic Keys
     13. Ciphers
14. Research
     15. Modern Cryptography
          16. Cryptographic Secrecy
          17. Symmetric Key Encryption
          18. Asymmetric Key Encryption
19. Projects
     20. Networking Analysis
     21. Malware Traffic Analysis
     22. Web Application Security Testing

## Introduction
---
**Cryptography** is the science of securing information through encryption and decryption. It has existed for thousands of years, evolving from simple substitution methods to highly complex systems that ensure confidentiality and are virtually impossible to break with current technology.

### Historical Cryptography
---
Before the advent of modern computers, cryptographic methods relied on techniques that didn't involve complex mathematics. Instead, they focused on ways to scramble or obscure text to protect its meaning. A cipher is a tool or method used to rearrange or disguise characters, making the original message unreadable. **Ciphering** refers to the act of applying such a method to encode a message. In this section, we’ll explore two main types of these traditional, non-mathematical cryptographic techniques.

#### Substitution Ciphers
---
A **substitution cipher** is a method of encryption that replaces each character or symbol in a message with another. This technique is relatively simple and one of the oldest forms of cryptography. A well-known example is the Caesar cipher, which is believed to have been used by Julius Caesar. This cipher works by shifting each letter in the alphabet by a fixed number of positions. For instance, with a shift of three, A becomes D, B becomes E, and so on. At the end of the alphabet, it wraps around—so Y becomes B and Z becomes C.

Although Caesar used Latin, the same method can be applied to other languages like English. For example, the word ```HELLO FRIEND``` becomes ```OLSSV MYPLUK``` when each letter is shifted three positions to the right. To decrypt a Caesar cipher, you simply reverse the process, shifting each letter in the ciphertext three places to the left to retrieve the original message.
##### ROT13
ROT13 is a simple cipher that shifts each letter 13 places in the alphabet, and like the Caesar cipher, it's easy to break. While too basic for modern use, these techniques laid the groundwork for today's encryption methods, which use more complex and layered substitutions to enhance security.
#### Polyalphabetic Substitution
---
A **polyalphabetic substitution cipher** is an encryption method that uses multiple substitution alphabets to encode a message. Unlike simple substitution ciphers (like Caesar or ROT13), which use only one fixed alphabet to replace each letter, polyalphabetic ciphers switch between several alphabets, making them much harder to break.
In a **monoalphabetic cipher**, each letter of the plaintext is always replaced by the same letter in the ciphertext. For example, if A becomes D, it will *always* be D. This predictable pattern is a vulnerability that cryptanalysts can exploit using frequency analysis. **Polyalphabetic ciphers** counter this weakness by using *different alphabets* at different points in the message. The most famous example is the **Vigenère cipher**. It uses a **keyword** to determine how letters are shifted.

##### How it works (simplified Vigenère example):
1. Choose a keyword: e.g., `KEY`
2. Repeat the keyword to match the length of the message:
   ```
   Plaintext:   A T T A C K A T D A W N
   Keyword:     K E Y K E Y K E Y K E Y
   ```
3. Convert each letter to its corresponding alphabet position (A=0, B=1, ..., Z=25), then shift the plaintext letter by the value of the keyword letter.

This method varies the substitution with each letter, making patterns much harder to detect.
##### Why It’s Stronger:
- **Frequency analysis** is less effective because the same letter in the plaintext may be encrypted as different letters in the ciphertext.
- It increases the complexity of the cipher depending on the length and randomness of the keyword.

#### Transposition Ciphers
---
A **transposition cipher** is a type of encryption where the positions of the characters in the plaintext are rearranged according to a certain system, but the actual characters themselves are not changed.
Unlike substitution ciphers, which **replace** characters with other characters, **transposition ciphers** **shuffle** the characters around. The goal is to obscure the original message by changing the order of the letters based on a specific pattern or key.

##### Simple Example:
Let’s take the message:
```
HELLO WORLD
```

And use a simple transposition rule: **write it in rows of 4 letters**:

```
H E L L  
O   W O  
R L D
```

Now read it column by column:

```
H O R E   L L W L D O
```

The ciphertext becomes:
```
HORELLWLD O
```

To decrypt it, the receiver must know the rule (e.g., "arrange in rows of 4, then read column-wise") and reverse the process.

##### Types of Transposition Ciphers:
- **Columnar Transposition**: The message is written in rows under a keyword, then read off by columns according to a pattern based on the keyword.
- **Rail Fence Cipher**: The message is written in a zigzag pattern across multiple "rails" and then read line by line.
- **Scytale Cipher** (used by ancient Spartans): A message is written on a strip of paper wrapped around a stick. Without the correct stick size (key), the message remains scrambled.

##### Why It’s Useful:
- It doesn’t change the actual letters, so frequency analysis isn’t immediately helpful.
- It can be combined with substitution ciphers for increased security—this is known as a **product cipher**.

#### Steganography
---
**Steganography** is the practice of hiding a secret message, file, or piece of information **within another non-secret file or message** to avoid detection. Unlike cryptography, which scrambles a message so it can’t be understood, steganography **hides the message’s existence entirely**. Steganography, derived from the Greek words *"steganos"* (meaning *covered* or *concealed*) and *"graphein"* (meaning *to write*), literally translates to "covered writing." It refers to the practice of hiding information in such a way that its very existence remains undetected. Unlike cryptography, which focuses on scrambling a message so it can't be read without a key, steganography conceals the message itself, making it invisible to an observer. This is often achieved by embedding data within seemingly ordinary files such as images, audio, video, or even text—so subtly that changes are imperceptible to the human senses. For instance, a picture might appear completely normal but actually contain hidden text encoded in the color values of certain pixels. In contrast to cryptographic methods, which are easily noticeable due to their encrypted, scrambled appearance, steganographic content blends in with its surroundings. However, the two techniques are frequently used in tandem: a message may be encrypted to protect its content, then hidden using steganography to conceal its existence. Steganography has many real-world applications, including digital watermarking for copyright protection, covert communication by journalists or whistleblowers, and even malicious uses such as hiding malware within seemingly harmless files during cyberattacks.

Applying accurate knowledge about cryptography equips students and users with a comprehensive understanding of its functions from both historical and modern perspectives. This body of knowledge is valuable for everyone to explore, as this journey is a shared learning experience—one through which I am also continuing to grow alongside others.
