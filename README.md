# Symmetric-Stream-Encryption
Encryption algorithm used in CS Project for A-Level. Not entirely secure but better than nothing.

Algorithm loosely based off of existing stream encryption algorithms. Research carried out from:
- https://en.wikipedia.org/wiki/Symmetric-key_algorithm
- https://www.schneier.com/academic/paperfiles/paper-twofish-paper.pdf

The Python OS module is used with urandom to gain a better seed for the random bit string for the key. HRNG is used to form a 32 byte (256 bit) key. Elements of the key are used based on: the index of the item in the list MOD the length of the key (32)... for each character in the text.

A random modulus is chosen to make the message slightly harder to decrypt.

The key, modulus, and message are then (re)encrypted using a permanent key ("encrypt") to hide the key and randomly selected modulus value. This adds a second layer of security but may be easily brute forced. It is possible that the algorithm may be reverse engineered from that point but not before.

Although the algorithm satisfies basic encryption requirements, it should not be used for industry/commercial purposes.
