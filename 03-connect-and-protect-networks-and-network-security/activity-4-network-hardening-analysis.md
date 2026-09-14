# Security Risk Assessment Report: Network Hardening Analysis

## Activity Overview
This activity focuses on conducting a security risk assessment for a social media organization following a major data breach that exposed sensitive customer data, including names and addresses. An audit of the organization's network revealed four critical vulnerabilities: employee password sharing, default database administrative credentials, lack of inbound/outbound firewall traffic rules, and an absence of multifactor authentication (MFA). To prevent future breaches, this assessment analyzes these security gaps and details three core network hardening controls—Firewall Maintenance, Multifactor Authentication (MFA), and Password Policies—required to secure the network infrastructure.

## Part 1: Select Up to Three Hardening Tools and Methods to Implement
The following methods should be implemented to secure the network:

* Firewall maintenance 
* Multifactor authentication (MFA) 
* Password policies 

Firewall maintenance involves checking and updating security configurations regularly to protect the system from potential threats. Additionally, firewall configuration can be modified to restrict abnormal traffic into the network and protect against various Distributed Denial of Service (DDoS) attacks. 

Multifactor authentication (MFA) requires two or more authentication factors to gain access to a system or network. It includes combinations such as a password, a PIN, a one-time password (OTP) sent to a mobile number or email, or a biometric fingerprint. Additionally, implementing MFA helps to protect the system against brute-force attacks, making it very difficult for an attacker to bypass authentication.

Enforcing password policies helps users select strong passwords and avoid using easily guessable credentials to protect the organization from brute-force attacks.

---

## Part 2: Explain Your Recommendations

Firewall maintenance should be done on a regular basis, and rules must be configured properly. This ensures the safety of the system, restricts unwanted traffic entering the network, and protects against various DDoS attacks. 

Enabling multifactor authentication (MFA) is one of the most critical security measures to protect the system from attack. When enabled, the system is protected by multiple factors such as a password, a one-time password (OTP), or a fingerprint. Even if a password is compromised, the attacker still requires an OTP or secondary authentication factor to gain access. Additionally, this directly mitigates the impact of brute-force attacks.

Creating and enforcing a password policy within a company is essential to secure systems against attackers. Enforcing policies such as setting a long minimum password length, prohibiting password reuse, blocking known breached passwords, and locking out accounts after several failed login attempts makes automated brute-force attacks ineffective.