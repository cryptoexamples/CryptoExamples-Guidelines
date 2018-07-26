# CryptoExamples-Guidelines

Guidelines for creating secure, complete, minimal, copyable and tested crypto code examples for [CryptoExamples](https://www.cryptoexamples.com).

By creating your *CryptoExample* you must follow these guidelines. Deviations are possible, but need to be justified.

## General

### Documentation (provided via Markdown file)

- [ ] Heading formatted like: $PROGRAMMING_LANGUAGE_NAME $SCENARIO using $LIBRARY_NAME
- [ ] Heading above code formatted like: Example Code for $HEADING_WITHOUT_USING_LIBRARY using $IMPORTANT_ALGORITHMS_AND_CONCEPTS
- [ ] Listed use cases for this code example/scenario
- [ ] Used long form of abbreviated terms the first time the abbreviation is used, except for headings 
- [ ] Stated used language versions
- [ ] Described additional requirements to make the example work (e.g. programming environment, operating system, other libraries than the standard library or needed configuration)
- [ ] Put references to official documentation sources for the used classes/methods/packages/modules
- [ ] Put references to official documentation sources for the used algorithms/concepts/parameters
- [ ] Put author name
- [ ] Removed previous review (changes invalidate a previous review of this example)
- [ ] Updated the `last_update` metadata
- [ ] Put appropriate tags

### Implementation / Example Code

#### Code

- [ ] Compliant with current coding guideline.
  - **Static code analysis**: use static code analysis tools such as ["Checkstyle"](http://checkstyle.sourceforge.net/), ["StyleCop"](https://archive.codeplex.com/?p=stylecop) or ["Pylint"](https://www.pylint.org/)
- [ ] Code can be executed with latest stable version of the programming language.
- [ ] Code can be executed with the latest stable version of the common tool chain of the programming language.
- [ ] Only uses algorithms and concepts that are secure.
  - **Static code analysis**: ["FindBugs"](http://findbugs.sourceforge.net/downloads.html), ["OWASP Dependency Check"](https://www.owasp.org/index.php/OWASP_Dependency_Check), ["Bandit"](https://pypi.org/project/bandit/)
- [ ] No standard library functionality can cover this scenario with all requirements of CryptoExamples.
- [ ] Import/Using statements are explicit (to avoid ambiguity if no fully qualified method/class names are used).
- [ ] Program output is made through a logging-facility (logger) and not via unfiltered system output like `System.out`/`print`/`echo`.
- [ ] Exceptions are caught except runtime exceptions.
- [ ] Exceptions are caught at the end (to not clutter the rest of the code).
- [ ] Exceptions are logged via the logging facility.
- [ ] No stack-trace is printed.
- [ ] The code demonstrates how its security functionality can be evaluated (e.g. by logging a conditional message that states the success or no success).
- [ ] The example code is tested with (a) unit test(s).
- [ ] Byte arrays are encoded for output.
- [ ] Strings are encoded using UTF-8.

#### Code comments / code documentation

- [ ] Class Documentation describes functionality.
- [ ] Class Documentation lists used algorithms and concepts.
- [ ] Inline comments describe essential (for non-security educated human beings) parts of the code.

## Scenario specific guidelines

### Choosing secure algorithms and concepts

- [ ] Consulted two trustworthy sources for choosing a specific algorithm. [National Institute of Standards and Technology (NIST)](https://www.nist.gov/), [BSI](https://www.bsi.bund.de/DE/Home/home_node.html), [Cryptographic Mechanisms: Recommendations and Key Lengths](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/TechGuidelines/TG02102/BSI-TR-02102-1.pdf?__blob=publicationFile&v=7)
- [ ] Consulted two trustworthy sources for choosing the keylength. [Keylength.com by BlueCrypt](https://www.keylength.com/en/compare/), [Cryptographic Mechanisms: Recommendations and Key Lengths](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/TechGuidelines/TG02102/BSI-TR-02102-1.pdf?__blob=publicationFile&v=7), [Recommendation for Key Management. Part 1: General](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-57pt1r4.pdf)

### Cryptographic Hashing / Message Digest

- [ ] Created or accepted a string to be hashed.
- [ ] Regarded the encoding of the string.
- [ ] Created the hash.
- [ ] Encoded the hash to be represented as string.

![hasing](pics/konzeptspezifischHashing.png)

### Symmetric Encryption

#### Key-based

- [ ] Created or accepted a plaintext string to be encrypted.
- [ ] Used a cryptographically suitable random number generator.
- [ ] Used an authenticated encryption algorithm.
- [ ] Regarded the encoding of the string.
- [ ] Encrypt the plaintext.
- [ ] Encoded the ciphertext to be represented as string.
- [ ] Decrypted the ciphertext.
- [ ] Encoded the decrypted bytes to be represented as string.

#### Password-based

- [ ] Created password or accepted a password to be used for encryption.
- [ ] Derived an appropirate key from the password using a secure method.
- [ ] Used a cryptographically suitable random number generator.
- [ ] Regarded the encoding of the string.
- [ ] Encrypt the plaintext.
- [ ] Encoded the ciphertext to be represented as string.
- [ ] Decrypted the ciphertext.
- [ ] Encoded the decrypted bytes to be represented as string.
- [ ] Salt for PBKDF2 (Password-Based Key Derivation Function 2) should be at least the size of the used hash function (e.g. 32 bytes for SHA-256).

![symmetric encryption](pics/konzeptspezifischSymmetrisch.png)

### Asymmetric Encryption
- [ ] Created or accepted a plaintext string to be encrypted.
- [ ] Created a key pair.
- [ ] Regarded the encoding of the string.
- [ ] Encrypt the plaintext with the public key.
- [ ] Encoded the ciphertext to be represented as string.
- [ ] Decrypted the ciphertext with the private key.
- [ ] Encoded the decrypted bytes to be represented as string.

![hasing](pics/konzeptspezifischAsymmetrisch.png)

### Signatures/Signing
- [ ] Created or accepted a plaintext string to be signed.
- [ ] Created a key pair.
- [ ] Regarded the encoding of the string.
- [ ] Create a signature with the private key.
- [ ] Used secure algorithms for signing.
- [ ] Encoded the signature to be represented as string.
- [ ] Verified the created signature with the help of the public key.

![hasing](pics/konzeptspezifischSignatur.png)

### Key Management

### Crypto Provider Setup/Configuration

## Language specific guidelines

- [ ] Named class like: Example$SCENARIO
- [ ] Defined example code method like: demonstrate$SCENARIO
- [ ] Example code method accepts appropriate parameter (usually String).
- [ ] The example only contains one defined method for the example demonstration AND a main method
- [ ] Main method calls the demonstrator method with parameter
- [ ] Return a result depending on the application output

### Java, C# specific guidelines

- [ ] Defined class as "public"
