# Overview of secure cryptographic algorithms and parameter choices

| | |
|- |- |- |
| **Hashing**| SHA-2: SHA-256/384/512 <br> SHA-3: SHA3-256/384/512  [[1]](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/TechGuidelines/TG02102/BSI-TR-02102-1.pdf?__blob=publicationFile&v=7), [[2]](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf)<br> Length >= 256 Bit (2018-2022, BSI) [[3]](https://www.keylength.com/en/compare/)|
|**Symmetric encryption**| |
|Key|>= 128 Bit (2018-2022, BSI) [[3]](https://www.keylength.com/en/compare/)|
|Modes|CTR, GCM [[1]](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/TechGuidelines/TG02102/BSI-TR-02102-1.pdf?__blob=publicationFile&v=7), [[4]](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-38a.pdf) |
|Blockcipher|AES-128/192/256 [[1]](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/TechGuidelines/TG02102/BSI-TR-02102-1.pdf?__blob=publicationFile&v=7), [[2]](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf)<br> Block-size >= 128 Bit  [[1]](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/TechGuidelines/TG02102/BSI-TR-02102-1.pdf?__blob=publicationFile&v=7)|
|Salt/Nonce|>= 128 Bit [[5]](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-132.pdf)|
|MAC|CMAC, GMAC, HMAC [[1]](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/TechGuidelines/TG02102/BSI-TR-02102-1.pdf?__blob=publicationFile&v=7), [[2]](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf)<br> Block-size >= 128 Bit, Tag-length >= 96 Bit [[1]](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/TechGuidelines/TG02102/BSI-TR-02102-1.pdf?__blob=publicationFile&v=7)|
|PBKDF2|HMAC [[5]](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-132.pdf)<br> Iteration >= 10.000 [[5]](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-132.pdf)|
|Authentificated encryption|GCM [[1]](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/TechGuidelines/TG02102/BSI-TR-02102-1.pdf?__blob=publicationFile&v=7)<br>(or Encrypt-then-MAC)|
|**Asymmetric encryption**|**RSA**: Key-length >= 2.000 Bit [[1]](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/TechGuidelines/TG02102/BSI-TR-02102-1.pdf?__blob=publicationFile&v=7)<br>(2.048 or 4.096 Bit [[6]](https://nvlpubs.nist.gov/nistpubs/specialpublications/nist.sp.800-57pt3r1.pdf)) <br> **ECIES**: Key-length >= 250 Bit (2018-2022, BSI) [[3]](https://www.keylength.com/en/compare/)<br>  **DLIES**: Key-length >= 2.000 Bit [[1]](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/TechGuidelines/TG02102/BSI-TR-02102-1.pdf?__blob=publicationFile&v=7)
