# CryptoExamples-Guidelines
Guidelines for creating secure, complete, minimal, copyable and tested crypto code examples

By creating your CryptoExample you should follow the [general](#general) guidelines for the external documentation and implementation. Also you should select the necessary [guideline depending on the language](#language) you want to work with. At last you should also read the [guideline](#useCase) with regard to the cryptographical use-case you want to implement.
<a name="general"></a>
## General

### External Documentation
1) Heading
- [ ] Name: "programming language""cryptographic use-case name" using "library name"

2) Use-case
- [ ] List of use-case for the following code example (at least one)

3) Requirements
- [ ] Used language version
- [ ] Optional: Notes on required programming environment and/or operating system
- [ ] Optional: required Edition (e.g. Java SE/ME)

4) Preparation
- [ ] If other libraries are used (in addition to the standard libraries), <br>
the main aspects which are necessary for the integration/configuration must be mentioned
- [ ] References to official sources (such as download or tutorial pages) should be given 

5) Heading for code example
- [ ] Name: Example Code for "Heading from 1)" using "used algorithms or concepts"

6) References
- [ ] Relevant official language-specific documentation which are explaining the used elements <br>
or algorithms in more detail

7) Author

8) Review

9) Tags
- [ ] Should include the used algorithms/concepts (at least the mentioned ones in 5)
- [ ] Used language/library


### Implementation
1) General
- [ ] The implementation should comply with current programming guidelines<br>
**Static code analysis possible**: use static code analysis tools such as<br>
["Checkstyle"](http://checkstyle.sourceforge.net/) (Java), ["StyleCop"](https://archive.codeplex.com/?p=stylecop) (C#) or ["Pylint"](https://www.pylint.org/)(Python)

- [ ] Implementation with the latest stable version of the programming language or the compilers
- [ ] Only uses algorithms and concepts that are secure<br>
**Static code analysis possible**: can also be used to detect security issues:<br>
["FindBugs"](http://findbugs.sourceforge.net/downloads.html) (Java), ["OWASP Dependency Check"](https://www.owasp.org/index.php/OWASP_Dependency_Check) (Java/C#), ["Bandit"](https://pypi.org/project/bandit/) (Python)

2) Selection of the library
- In the selection one should prefer the use of standard libraries.<br>
If another non-standard libraries should be used, the selection must <br>
be decided with regard to their security aspect and actuality

3) References to necessary libraries
- [ ] Explicitly specify all necessary imports

4) Definition of Logger
- [ ] Define (if not predefined) the format with the application name, time/date and severity level
- [ ] Definition outside the method at class level

5) Internal documentation
- Overall description
 - [ ] Above the actual technical implementation on class level
 - [ ] Describes functionality
 - [ ] List of algorithms used for implementation
- Inline comments
 - [ ] Description explains the decisions made within the code<br>
(should be done before every block with a specific functionality)
 - [ ] Restriction to a few words

 6) Exception handling
 - [ ] Interception of all errors within one statement
 - [ ] Errors are only caught, if they concern the concrete execution (no runtime exceptions)
 - [ ] Only catch specific and necessary errors
 - [ ] Define one standard error message as output (no customized error messages)
 - [ ] Output error messages with the logger (on "SEVERE" level)
 - [ ] Avoid the output of the entire stack trace

7) Program output
- [ ] Implement a test that shows that the implemented use-case is functional.<br>
E.g. comparison of the plain with decrypted cipher
- [ ] Output the result (e.g. as a truth value) via the logger (on the "INFO" level)

8) Encoding
- [ ] Use an encoding according to the current standard for the representation of byte arrays<br>
(e.g. Base64)
- [ ] Use an encoding according to the current standard for the representation of the string<br>
(e.g. Utf-8)


<a name="language"></a>
## Language dependent guidelines

- [Java or C#](Java.md)
- [Python](Python.md)

<a name="useCase"></a>
## Use-case dependent guidelines
In the generation of cryptographic code it is essential to find out which algorithms and concepts should be used to implement the selected use-case in a secure way. Therefore it is highly recommended to inform yourself which is the state of the art in the cryptography before the creation of your CryptoExamples:
- [How to choose secure algorithms and concepts](Algorithms.md)


### Hashing
- [ ] Create an instance that executes the selected hash function
- [ ] Generate Hash
- [ ] Convert Hash to String

<center><img src=".\pics\konzeptspezifischHashing.png" alt="Guideline Hashing" width="300px" /> </center>

### Symmetric Encryption
<a name="keyBased"></a>
- **Key-based**

 1) Generation of key and nonce
 - [ ] Use a cryptographically suitable random number generator

 2) Creation of an encryption instance
 - [ ] Use an authenticated encryption algorithm
 - [ ] Encrypt the plain

 3) Creation of a decryption instance
 - [ ] Use the same configurations as in 2)
 - [ ] Decrypt the cipher

- **Password-based**
Step 1) of the [above guideline](#keyBased) must be replaced as follows:

 1) Optional: Create password (if not already available)
  - [ ] Generate a temporary key
  - [ ] Create string representation of the temporary key, which is used as password

 2) Derivation of the key from the password
  - [ ] Choose a key derivation function
  - [ ] Generation Salt
   - [ ] Use a cryptographically suitable random number generator
  - [ ] Choose an appropriate number of iterations
  - [ ] Select cryptographic function (Pseudorandom Function (PRF))
  - [ ] Choose the desired final key length

Then all further steps from 2) [key-based](#keyBased) follow as already described.

- **File encryption**

 1) Generation of key and nonce
 - [ ] Use a cryptographically suitable random number generator

 2) File encryption
 - [ ] Read from file that should be encrypted
 - [ ] Define the encryption instance
   - [ ] Use an authenticated encryption algorithm
 - [ ] Encrypt the read bytes
 - [ ] Write encrypted bytes to an "enc" file

 3) file decryption
 - [ ] Read from file encrypted enc file
 - [ ] Creation of a decryption instance
   - [ ] Use the same configurations as in 2)
 - [ ] Decrypt the read bytes
 - [ ] Write decrypted bytes to a corresponding file

<img src=".\pics\konzeptspezifischSymmetrisch.png" alt="Guideline Hashing" width="550px" />

### Asymmetric Encryption

### Signatures/Signing

### Key Management

### Crypto Provider Setup/Configuration

