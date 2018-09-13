# Overview of secure cryptographic algorithms and parameter choices

| Concept | Choices | Sources |
| ------- | ------- | ------- |
| **Hashing**| SHA<sup>1</sup>-2: SHA-256/384/512 <br> SHA-3: SHA3-256/384/512  <br> Length >= 256 Bit (2018-2022, BSI) | [1] (2018-2022), [2], <br>[3] (BSI, 2018-2022), [4]|
|**Symmetric encryption**| ||
|Blockcipher|AES<sup>2</sup>-128/192/256 <br> Block-size >= 128 Bit |[1] (2018-2022), [2], [4]|
|Modes|CCM<sup>3</sup>, GCM<sup>4</sup> <br>(only authenticated encryption)|[1] (2018-2022), [4], [5] |
|Key|>= 128 Bit |[3] (2018-2022, BSI) |
|Salt/Nonce|>= 128 Bit <br> (depending on the chosen algorithm)|[6]|
|MAC<sup>5</sup>|CMAC, GMAC, HMAC <br> Block-size >= 128 Bit,<br> Tag-length >= 96 Bit |[1] (2018-2022), [2]|
|**Password derivation**| | |
|PBKDF2<sup>6</sup>|HMAC <br> Iteration >= 10.000 |[6]|
|**Asymmetric encryption**| | |
|RSA<sup>7</sup>| Key-length >= 2.000 Bit<br>(2.048 or 4.096 Bit) | [1] (2018-2022), [4], [7]|
|ECIES<sup>8</sup>| Key-length >= 250 Bit |[3] (BSI, 2018-2022)|
|DLIES<sup>9</sup>| Key-length >= 2.000 Bit |[1] (2018-2022)|

Last update:  / Next update:<br>
### Abbreviations:
<sup>1</sup> : Secure Hash Algorithm<br>
<sup>2</sup> : Advanced Encryption Standard<br>
<sup>3</sup> : Counter with CBC-MAC<br>
<sup>4</sup> : Galois/Counter Mode<br>
<sup>5</sup> : (Galois/Cipher-based/Hash-based) Message Authentication Code<br>
<sup>6</sup> : Password-Based Key Derivation Function 2<br>
<sup>7</sup> : Rivest Shamir Adleman<br>
<sup>8</sup> : Elliptic Curve Integrated Encryption Scheme<br>
<sup>9</sup> : Discrete Logarithm Integrated Encryption Scheme

[1]: https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/TechGuidelines/TG02102/BSI-TR-02102-1.pdf?__blob=publicationFile&v=7
[2]: https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf
[3]: https://www.keylength.com/en/compare/
[4]: https://www.iana.org/assignments/tls-parameters/tls-parameters.xhtml#tls-parameters-4
[5]: https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-38a.pdf
[6]: https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-132.pdf
[7]: https://nvlpubs.nist.gov/nistpubs/specialpublications/nist.sp.800-57pt3r1.pdf
