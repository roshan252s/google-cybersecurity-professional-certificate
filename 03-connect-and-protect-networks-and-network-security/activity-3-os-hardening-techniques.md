# Cybersecurity Incident Report: Apply OS Hardening Techniques

## Incident Overview
This report documents a security incident where the company website (`yummyrecipesforme.com`) was compromised by an attacker via a brute-force attack. Network logs and file behaviors were analyzed to determine how unauthorized changes were made, how malicious scripts altered visitor traffic, and what security controls failed.

---

## Section 1: Identify the Network Protocol Involved in the Incident

The primary network protocol involved in this incident is **HyperText Transfer Protocol (HTTP)**. 

HTTP operates at the Application layer of the OSI model. During the incident, HTTP was used to establish the connection with the website, request web pages, and deliver the malicious executable file to the visitors' browsers.

---

## Section 2: Document the Incident

### Initial Customer Reports
Multiple customers emailed `yummyrecipesforme`'s helpdesk complaining that the company's website (`yummyrecipesforme.com`) had prompted them to download a file to access free recipes. After running the file, customers mentioned that their computers began running more slowly. 

### Administrative Impact
In response to this incident, the owner tried to log in to the admin panel, but the password to the admin account had been changed. As a result, the owner was unable to get access and reached out to the website hosting provider.

### Sandbox & Log Analysis
To address this incident, a cybersecurity analyst used a sandbox environment to observe the suspicious website behavior and ran `tcpdump` to analyze the network traffic:

* **Initial Connection:** The browser initiated a DNS request for the IP address of `yummyrecipesforme.com` from the DNS server. After receiving the correct IP address, the browser initiated an HTTP request for the webpage.
* **Malicious File Prompt:** When the website loaded, the analyst was prompted to download an executable file to update the browser. 
* **Execution & Redirection:** When accepted and run, the analyst noticed a sudden change in network traffic as the browser initiated the download of an executable file and a DNS request for a different website called `greatrecipesforme.com`. The network traffic was then rerouted to the new website after receiving its IP address from the DNS server.

### Root Cause Analysis
A senior analyst confirmed that the website had been compromised and checked the source code for the website:

* **Unauthorized Script Injection:** The analyst discovered that JavaScript code had been added to prompt website visitors to download an executable file. Additionally, a script in that file redirected visitors' browsers from `yummyrecipesforme.com` to `greatrecipesforme.com`.
* **Brute-Force Exploitation:** The cybersecurity team reported that the web server was impacted by a brute-force attack because the hacker was able to guess the password easily since the admin password was still set to the default password. 
* **Account Takeover:** As a result, the attacker gained access to the system, implanted the script, and changed the password to lock out legitimate administrators.

---

## Section 3: Recommend Remediations for Brute-Force Attacks

To protect system resources and prevent future unauthorized access through brute-force attacks, the following security controls should be implemented:

* **Prohibit Password Reuse:** Restrict users and administrators from reusing previous passwords to ensure compromised credentials cannot be recycled.
* **Enforce Password Complexity:** Require strong passwords combining letters, symbols, and numbers to make passwords significantly harder for attackers to guess.
* **Implement Multi-Factor Authentication (MFA):** Require both a password and a time-sensitive one-time password (OTP), adding a critical layer of defense that brute-force attacks cannot easily bypass.