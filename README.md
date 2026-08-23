# Artemis Financial Secure Software Project

## Client and Software Requirements

Artemis Financial is a financial consulting company that wanted to modernize its web application while improving the security of client and financial information. The primary goal was to add secure communication and data verification to the existing application. This included implementing a checksum using SHA-256, generating a certificate, and converting the application from HTTP to HTTPS.

## Software Security and Vulnerability Assessment

I used both manual code review and OWASP Dependency-Check to evaluate the security of the application. One thing I did well was verify the security of the application before and after making changes rather than assuming the refactored code was secure. Secure coding is important because vulnerabilities can expose sensitive information, interrupt services, and damage customer trust. For a financial company, protecting client information is especially important to the overall reliability and reputation of the organization.

## Challenges and Lessons Learned

One of the most challenging parts of the project was Dependency-Check. The original project used an older version of the Maven plug-in that could no longer successfully retrieve the required vulnerability information. Updating the plug-in allowed the scan to complete successfully. This taught me that troubleshooting security tools and keeping them current are also important parts of secure software development.

## Layers of Security

I added multiple layers of security to the application. SHA-256 was implemented to generate a checksum for data-integrity verification. I also generated a self-signed certificate and PKCS12 keystore and configured the application to use HTTPS on port 8443. In future projects, I would continue using automated vulnerability scanners along with manual code review and functional testing to identify vulnerabilities and determine appropriate mitigation techniques.

## Functional and Security Testing

After refactoring, I compiled and ran the application to verify that it operated without errors. I tested the `/hash` endpoint to confirm that it generated the expected SHA-256 checksum and verified that the application successfully operated through HTTPS.

I also ran OWASP Dependency-Check against both the original and refactored versions of the application using the same Dependency-Check version. The results matched, demonstrating that my security changes did not introduce additional dependency vulnerabilities.

## Tools and Practices

The main tools and practices I used included:

* Java and Eclipse
* Maven
* Java Keytool
* SHA-256 and Java `MessageDigest`
* HTTPS and SSL/TLS configuration
* PKCS12 keystore and certificate management
* OWASP Dependency-Check
* Manual code review
* Functional and security testing

These tools and practices will be useful in future software development and cybersecurity projects, particularly when working with secure communications and vulnerability assessment.

## Portfolio Value

I would show future employers the refactored Artemis Financial application as an example of my secure software development skills. The project demonstrates my ability to implement checksum verification, configure HTTPS, work with certificates and keystores, perform vulnerability scanning, troubleshoot security tools, and verify that security changes do not introduce additional vulnerabilities. It demonstrates both Java development skills and an understanding of secure software development practices.
han my ability to write Java code. It shows that I can identify security concerns, implement security improvements, test those improvements, troubleshoot development tools, and verify that an application remains functional after being modified.
