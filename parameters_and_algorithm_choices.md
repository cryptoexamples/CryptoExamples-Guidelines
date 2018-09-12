# Overview of secure cryptographic algorithms and parameter choices

| Concept | Choices | Sources |
| ------- | ------- | ------- |
| **Hashing**| SHA-2: SHA-256/384/512 <br> SHA-3: SHA3-256/384/512  <br> Length >= 256 Bit (2018-2022, BSI) | [[1]](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/TechGuidelines/TG02102/BSI-TR-02102-1.pdf?__blob=publicationFile&v=7) (2018-2022), [[2]](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf), <br>[[3]](https://www.keylength.com/en/compare/)(BSI, 2018-2022), [[4]](https://www.iana.org/assignments/tls-parameters/tls-parameters.xhtml#tls-parameters-4)
|**Symmetric encryption**| ||
|Blockcipher|AES-128/192/256 <br> Block-size >= 128 Bit |[[1]](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/TechGuidelines/TG02102/BSI-TR-02102-1.pdf?__blob=publicationFile&v=7) (2018-2022), [[2]](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf),  [[4]](https://www.iana.org/assignments/tls-parameters/tls-parameters.xhtml#tls-parameters-4)|
|Modes|CTR, GCM |[[1]](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/TechGuidelines/TG02102/BSI-TR-02102-1.pdf?__blob=publicationFile&v=7) (2018-2022), [[4]](https://www.iana.org/assignments/tls-parameters/tls-parameters.xhtml#tls-parameters-4), [[5]](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-38a.pdf) |
|Key|>= 128 Bit |[[3]](https://www.keylength.com/en/compare/) (2018-2022, BSI) |
|Salt/Nonce|>= 128 Bit <br> (depending on the chosen algorithm)|[[6]](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-132.pdf)|
|MAC|CMAC, GMAC, HMAC <br> Block-size >= 128 Bit,<br> Tag-length >= 96 Bit |[[1]](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/TechGuidelines/TG02102/BSI-TR-02102-1.pdf?__blob=publicationFile&v=7) (2018-2022), [[2]](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf)|
|PBKDF2|HMAC <br> Iteration >= 10.000 |[[6]](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-132.pdf)|
|Authentificated encryption|GCM <br>(or Encrypt-then-MAC)|[[1]](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/TechGuidelines/TG02102/BSI-TR-02102-1.pdf?__blob=publicationFile&v=7) (2018-2022), [[4]](https://www.iana.org/assignments/tls-parameters/tls-parameters.xhtml#tls-parameters-4)|
|**Asymmetric encryption**|||
|RSA| Key-length >= 2.000 Bit<br>(2.048 or 4.096 Bit) | [[1]](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/TechGuidelines/TG02102/BSI-TR-02102-1.pdf?__blob=publicationFile&v=7), [[4]](https://www.iana.org/assignments/tls-parameters/tls-parameters.xhtml#tls-parameters-4), [[7]](https://nvlpubs.nist.gov/nistpubs/specialpublications/nist.sp.800-57pt3r1.pdf)|
|ECIES| Key-length >= 250 Bit |[[3]](https://www.keylength.com/en/compare/) (BSI, 2018-2022)|
|DLIES| Key-length >= 2.000 Bit |[[1]](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/TechGuidelines/TG02102/BSI-TR-02102-1.pdf?__blob=publicationFile&v=7) (2018-2022)|

Last update:  / Next update:
