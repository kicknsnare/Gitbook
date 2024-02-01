# S/MIME (Secure/Multipurpose Internet Mail Extensions)

_Widely accepted protocol for sending digitally signed and encrypted messages_.

Using [Public Key Cryptography](https://www.ibm.com/docs/en/ztpf/2023?topic=concepts-public-key-cryptography), S/MIME guarantees data integrity and nonrepudiation.&#x20;

* If Bob wishes to use S/MIME, then he'll need a digital certificate. This digital certificate will contain his public key.&#x20;
* With this digital certificate, Bob can "sign" the email message with his private key.&#x20;
* Mary can then decrypt Bob's message with Bob's public key.&#x20;
* Mary will do the same (send her certificate to Bob) when she replies to his email, and Bob complete the same process on his end.
* Both will now have each other's certificates for future correspondence.&#x20;

<figure><img src="https://tryhackme-images.s3.amazonaws.com/user-uploads/5c549500924ec576f953d9fc/room-content/27cb0b439d172324f453e57c9cbf7ac0.png" alt=""><figcaption></figcaption></figure>
