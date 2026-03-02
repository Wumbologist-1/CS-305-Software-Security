# CS 305 – Module Eight Journal  
## Artemis Financial Security Portfolio Reflection  
**Luis Tomassini**

---

## Overview

This portfolio artifact reflects my work on securing software for Artemis Financial. Across Projects One and Two, I conducted a vulnerability assessment, implemented secure coding practices, refactored insecure configurations, and validated security improvements through testing tools and encrypted communications. This README documents my reflection on that process.

---

## Client Summary and Software Requirements

Artemis Financial is a financial services company that required improvements to its software security posture. The application initially operated without encrypted communication and lacked integrity verification mechanisms. This posed risks related to data interception, tampering, and exposure of sensitive client information.

The primary issue to address was securing client-server communications and implementing proper cryptographic protections. The company required a vulnerability assessment of its application, identification of security weaknesses, and refactoring of the codebase to ensure compliance with secure coding standards and encrypted transmission protocols.

---

## Identifying Security Vulnerabilities

When reviewing the application, I identified several core security concerns:

- Communication over HTTP instead of HTTPS
- Lack of cryptographic hashing for integrity validation
- Potential exposure to interception or man-in-the-middle attacks
- Absence of dependency vulnerability scanning

I approached the vulnerability assessment methodically, analyzing configuration files, reviewing the application’s transport layer setup, and identifying weaknesses in encryption implementation.

Coding securely is essential because software security directly affects data confidentiality, integrity, and availability. In financial systems especially, vulnerabilities can result in financial loss, regulatory penalties, and reputational damage. Secure software adds measurable value by reducing organizational risk and strengthening customer trust.

---

## Challenges in the Vulnerability Assessment

The most challenging part of the vulnerability assessment was understanding how configuration-level weaknesses can introduce systemic risk. It required more than simply reviewing source code. It required evaluating how the application was deployed and how it communicated over a network.

Implementing TLS correctly required attention to keystore configuration, certificate generation, and proper Spring Boot property settings. Debugging SSL misconfigurations reinforced the importance of understanding both application-level code and infrastructure-level security.

---

## Increasing Layers of Security

To increase layers of security, I implemented a defense-in-depth strategy:

- Added SHA-256 hashing to verify data integrity
- Generated a 2048-bit RSA self-signed certificate
- Configured HTTPS on port 8443
- Disabled unsecured communication pathways
- Performed static analysis using OWASP dependency-check

In future projects, I would expand this process by incorporating:

- Automated CI/CD security scanning
- Static application security testing (SAST)
- Dynamic application security testing (DAST)
- Penetration testing frameworks
- Code quality analysis tools such as SonarQube

Security must be continuous rather than reactive. Future assessments would involve integrating security scanning directly into development pipelines.

---

## Ensuring Functional and Secure Code After Refactoring

After refactoring the code to implement encryption and hashing, I validated both functionality and security.

To ensure the application remained functional:
- I executed the application and confirmed successful startup.
- Verified HTTPS connectivity through the browser.
- Confirmed checksum generation produced consistent SHA-256 results.

To ensure no new vulnerabilities were introduced:
- I ran the OWASP dependency-check Maven plugin.
- Reviewed the generated HTML vulnerability report.
- Confirmed build success and absence of critical dependency issues.

Successful HTTPS execution on port 8443 and build success confirmation demonstrated that the refactoring did not introduce runtime errors or configuration instability.

---

## Tools, Resources, and Practices Used

Several tools and practices were essential in this project:

- **Java Keytool** for certificate generation
- **SHA-256 hashing** for integrity validation
- **Spring Boot SSL configuration**
- **OWASP Dependency-Check** for static vulnerability analysis
- **Maven build lifecycle management**
- Secure configuration management principles

These tools reinforced secure development lifecycle practices and demonstrated practical DevSecOps integration within a Java-based application.

---

## Demonstrating Skills to Future Employers

From this assignment, I can demonstrate:

- Ability to conduct structured vulnerability assessments
- Implementation of TLS encryption using certificates
- Cryptographic hashing using SHA-256
- Secure configuration of Java Spring Boot applications
- Integration of security scanning tools into development workflows
- Practical application of defense-in-depth security principles

This artifact represents more than theoretical understanding. It demonstrates applied secure coding, vulnerability mitigation, and security validation techniques within a real-world software development environment.

---

## Closing Reflection

This project strengthened my understanding of how application security spans multiple layers, from cryptographic algorithms to deployment configuration and dependency management. It reinforced the importance of integrating security early in the development lifecycle rather than treating it as an afterthought.

Security is not a single feature but a design philosophy. Through this assignment, I gained practical experience implementing encryption, validating integrity, and assessing risk within a structured vulnerability assessment framework.

---
