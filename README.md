

The client for this project was Artemis Financial, a financial consulting company that wanted to modernize its software while improving the protection of client data and financial information. The company has a public web interface, so secure communication was an important concern. Artemis Financial wanted Global Rain to improve the security of its existing application by adding a file verification step using a checksum and securing communication between the client and server. The application also needed to be tested for vulnerabilities after the security improvements were implemented.

#### What did you do well when you found your client's software security vulnerabilities? Why is it important to code securely? What value does software security add to a company's overall well-being?

One thing I did well was use multiple methods to evaluate the security of the application instead of relying on only one tool. I manually reviewed the code and also used OWASP Dependency-Check to identify vulnerabilities associated with the application's dependencies. I was careful to distinguish between vulnerabilities that were already present in the supplied application and vulnerabilities that could have been introduced through my changes.

Secure coding is important because vulnerabilities can expose sensitive information or allow an attacker to interfere with an application. This is especially important for a financial company because customers expect their personal and financial information to be protected. Strong software security can reduce the possibility of data breaches, financial losses, service interruptions, and damage to the company's reputation. It can also help maintain customer trust in the organization.

### Which part of the vulnerability assessment was challenging or helpful to you?

The Dependency-Check portion was one of the more challenging parts of the project. The original project used an older version of the OWASP Dependency-Check Maven plug-in, and the scan initially failed because it attempted to retrieve vulnerability information using an outdated NVD data source. After updating the Dependency-Check plug-in, I was able to successfully complete the scan.

This was also one of the most helpful parts of the project because it showed me that security tools themselves have to be maintained. A security test failing does not necessarily mean that the application code is incorrect. Sometimes the testing environment or tool configuration needs to be investigated before making changes to the application.

### How did you increase layers of security? In the future, what would you use to assess vulnerabilities and decide which mitigation techniques to use?

I increased the application's security by adding multiple layers instead of relying on one security control. I implemented SHA-256 checksum verification to help verify data integrity. I generated a self-signed certificate and PKCS12 keystore and configured the application to communicate through HTTPS on port 8443. HTTPS protects information while it is being transmitted, while the checksum provides a way to determine whether data has been changed.

In the future, I would continue combining automated vulnerability scanning with manual code review and functional testing. Tools such as OWASP Dependency-Check can identify known vulnerabilities in third-party components, while manual review can identify logical and security problems that an automated scanner might not recognize. I would evaluate the severity and relevance of each vulnerability before selecting a mitigation technique rather than automatically changing or suppressing every finding.

### How did you make certain the code and software application were functional and secure? After refactoring the code, how did you check to see whether you introduced new vulnerabilities?

I tested the application after refactoring to make sure it compiled and executed without errors. I verified that the `/hash` endpoint successfully generated a SHA-256 checksum from my unique data string. I also confirmed that the Spring Boot server successfully started on HTTPS port 8443 and that I could access the endpoint at `https://localhost:8443/hash`.

I also performed OWASP Dependency-Check testing after completing the refactoring. To determine whether my changes introduced additional dependency vulnerabilities, I ran the same version of Dependency-Check against a clean copy of the original Project Two application and compared those findings with the refactored version. The results matched. This showed that the vulnerabilities identified in the final report were already associated with the supplied dependencies and that my SHA-256 and HTTPS changes did not introduce additional dependency vulnerabilities.

### What resources, tools, or coding practices did you use that might be helpful in future assignments or tasks?

Several tools and practices from this project will be useful in future software development assignments. I used Eclipse for development, Maven for building and managing the project, Java Keytool for generating the certificate and keystore, and OWASP Dependency-Check for static vulnerability testing. I also gained more experience using Java's `MessageDigest` functionality to implement SHA-256.

The project also reinforced the importance of using established security libraries instead of attempting to create custom cryptographic solutions. Other useful practices included testing after making changes, comparing security results before and after refactoring, using HTTPS for sensitive communications, and reviewing code manually in addition to using automated security tools.

### Employers sometimes ask for examples of work that you have successfully completed to show your skills, knowledge, and experience. What might you show future employers from this assignment?

I could use the refactored Artemis Financial application as an example of my ability to apply secure coding practices to an existing software project. I could demonstrate how I implemented SHA-256 checksum verification, configured a Java application to communicate through HTTPS, generated and configured a certificate and keystore, and performed vulnerability testing with OWASP Dependency-Check.

I could also discuss the troubleshooting involved in getting Dependency-Check to work and how I compared the original and refactored applications to verify that my changes did not introduce new dependency vulnerabilities. This project demonstrates more than my ability to write Java code. It shows that I can identify security concerns, implement security improvements, test those improvements, troubleshoot development tools, and verify that an application remains functional after being modified.
