# Portfolio Activity: Use the NIST Cybersecurity Framework to Respond to a Security Incident

## Activity Overview
Following a Denial of Service (DoS) attack that disrupted internal network access for two hours, this security incident report analyzes the breach using the National Institute of Standards and Technology (NIST) Cybersecurity Framework (CSF). The report outlines the root cause of the incident and details actionable measures across the Identify, Protect, Detect, Respond, and Recover functions to harden the organization's network against future threats.
---

## Summary
A multimedia organization offering web design services, graphic design, and social media marketing solutions experienced a DoS attack, which compromised the internal network for two hours until it was resolved. During the attack, normal internal network traffic could not access any network resources because of an incoming flood of ICMP packets. To overcome this, the incident management team blocked all incoming ICMP packets, stopped all non-critical network services offline, and restored critical network services. After investigating, the cybersecurity team found that a flood of ICMP pings had been sent to the company’s network through an unconfigured firewall. This vulnerability allowed the malicious actor to compromise the company’s network through a denial of service (DoS) attack. To address this weakness, the network security team implemented a new firewall rule to limit the rate of incoming ICMP packets, network monitoring software to detect abnormal traffic patterns, and an IDS/IPS system to filter out some ICMP traffic based on suspicious characteristics.

---

## NIST Cybersecurity Framework Analysis

### Identify
A DoS attack occurred due to the incoming flood of ICMP packets into the company’s network through an unconfigured firewall. Due to this, normal internal network traffic could not access any network resources for two hours.

### Protect
To protect the assets of the organization from such events in the future, a new firewall rule should be implemented to limit the rate of incoming ICMP packets. Additionally, source IP address verification should be configured on the firewall to check for and block spoofed IP addresses on incoming ICMP packets.

### Detect
The team should implement network monitoring software to detect abnormal traffic patterns and an IDS/IPS system to filter out some ICMP traffic based on suspicious behavior.

### Respond
In case of any such security events, the team should block all incoming ICMP packets to contain the threat and mitigate data loss. Additionally, they should take non-critical network services offline and restore critical network services.

### Recover
The team should systematically recover the affected network resources, restore impacted systems to full operational status, and verify data integrity for any systems affected during the attack.