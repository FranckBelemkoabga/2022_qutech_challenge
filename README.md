# QuTech Challenges @ MIT iQuHACK 2022

<p align="left">
  <a href="https://qutech.nl" target="_blank"><img src="https://user-images.githubusercontent.com/10100490/151484481-7cedb7da-603e-43cc-890c-979fb66aeb60.png" width="25%" style="padding-right: 0%"/></a>
  <a href="https://iquhack.mit.edu/" target="_blank"><img src="https://user-images.githubusercontent.com/10100490/151647370-d161d5b5-119c-4db9-898e-cfb1745a8310.png" width="10%" style="padding-left: 0%"/> </a>
</p>

## Description
In solving QuTech’s Quantum Key Distribution Challenge, we developed a secure messaging system based on QKD. We implement QKD based on Ekert-91 (E91) protocol and demonstrate along with text and email encryption applications. 

### QKD Algorithm
We chose Ekert-91 (E91), a protocol that utilizes two properties of entanglement generated by a common source, to distribute the sifted key between two parties Alice and Bob with the presence of an eavesdropper Eve. The entangled states are either perfectly correlated or perfectly non-correlated, which emphasizes that the two parties have directionality synchronization. Moreover, any eavesdropping attempts by Eve can be detected as they destroy the correlations between Alice and Bob.
Our implementation of said algorithm can be found in module 'E91.py.' It is tested using the Quantum Inspire emulator and it successfully returns a sifted key. The key can then be utilized for a variety of our encryption needs. 

### Text-Encryption Module and Applications
Our group members, all Duckduckgo users, highly value internet privacy. With the onset of quantum computing, the potential of leveraging quantum computers to break RSA-based encryptions, a task that would take a traditional computer 300 million years to complete, has become theoretically realizable within 8 hours (posits this MIT article). Thus, the future of encryption should also turn to quantum computing and quantum encryption algorithms. As such, we have developed an encryption module, leveraging the key distributed by our QKD algorithm, which we intend to utilize for a variety of encryption purposes. 
Our encryption algorithm is implemented in module encrypt.py, which contains two main functions: encrypter and decrypter. Function [encrypter] uses the key generated via our QKD algorithm to encrypt a message [fullmsg] according to the specifications of AES (Advanced Encryption Standard). Function decrypter uses this key to perform the decryption tasks.
In conjunction with these encryption algorithms, we have also developed three main applications. The first, implemented in serverclient.py, is a server-client command-line interface for sending secure messages from one IP to another. The second, which provides secure emailing functionality, allows users to send entire emails (subjects, bodies, and attachments) encrypted by a QKD generated key and leveraging AES (Advanced Encryption Standard). It is implemented in encrypted_email.py. Lastly, we have also developed a website with chatting capabilities. 

### Website
The chat website is programmed using Django. It contains all HTML, CSS, Python and javascript files. The website is used for the users to securely chat with each other. First there is a room name and then they add their name. Once inside the room a person can send a message. Now when a message is sent, information such as username, message content, and ip address is passed to the chatting server which will then safely encrypt the message. This chatting server gets the key from the Quantum Key Distribution making it safe and secure.

### Website
The chat website is programmed using Django. It contains all HTML, CSS, Python and javascript files.
The website is used for the users to securely chat with each other. First there is a room name and then they add their name. Once inside the room a person can send a message. Now when a message is sent, information such as username, message content, and ip address is passed to the chatting server which will then safely encrypt the message. This chatting server gets the key from the Quantum Key Distribution making it safe and secure. 

## Future Plans
We intend to gear our encryption applications towards aiding domestic abuse victims, whose lines of communication are often monitored by their aggressors. 
## Resources:
### What QKD does?
“Quantum key distribution is only used to produce and distribute a key, not to transmit any message data. This key can then be used with any chosen encryption algorithm to encrypt (and decrypt) a message, which can then be transmitted over a standard communication channel. The algorithm most commonly associated with QKD is the one-time pad, as it is provably secure when used with a secret, random key. In real-world situations, it is often also used with encryption using symmetric key algorithms like the Advanced Encryption Standard algorithm.”

### Protocols
1. BB84 Protocol: Using randomly X basis and Z basis.
2. B92 Protocol: Simplified BB84 protocol.
3. Eckert's Protocol E91: Using quantum teleportation and Bell states instead of superposition.

### Privacy Amplification
“Since there is some error, we must assume that Eve may have successfully learned some of the key's bits. QKD protocols can employ a technique known as privacy amplification to reduce the information Eve has about the key down to an arbitrary level.”
