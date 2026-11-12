# NETWORKWALKS-VUYANI-MKHIZE-B084-WK2-PM-FINAL-CYBERSECURITY-PENETRATION-TEST-REPORT

# WEEK 2 – PROJECT MODULE 1
# Footprinting and Reconnaissance Using Multiple Kali Linux Tools

## 1. Project Overview

This project focuses on practical website footprinting and reconnaissance using multiple tools available in Kali Linux.

The exercise explores how publicly accessible information can be collected from a target domain to understand its registration details, DNS infrastructure, web technologies, HTTP response headers and security mechanisms.

The assessment uses six reconnaissance tools: WHOIS, WhatWeb, Nslookup, cURL, Wafw00f and DNSRecon.

**Project Details**

| Category | Description |
|---|---|
| Project | Week 2 – Project Module 1 |
| Domain | networkwalks.com |
| Project Area | Cybersecurity and Ethical Hacking |
| Assessment Type | Footprinting and Reconnaissance |
| Operating System | Kali Linux |
| Virtualisation Platform | Oracle VirtualBox |
| Tools | WHOIS, WhatWeb, Nslookup, cURL, Wafw00f and DNSRecon |

## 2. Objectives

The primary objectives of this practical exercise are to:

- Gather publicly available domain registration information.
- Identify technologies and software components used by a website.
- Resolve domain names into their corresponding IP addresses.
- Examine HTTP response headers and identify potentially exposed server information.
- Detect whether a Web Application Firewall (WAF) is present.
- Enumerate publicly accessible DNS records.
- Understand how reconnaissance information can be used during cybersecurity assessments.
- Develop practical experience using reconnaissance tools in Kali Linux.

## 3. Lab Environment

The practical exercise was conducted using Kali Linux running inside an Oracle VirtualBox virtual machine.

The environment provided access to the Linux terminal and the reconnaissance tools required to perform the assessment.

**Environment Configuration**

| Component | Configuration |
|---|---|
| Operating System | Kali Linux |
| Virtualisation | Oracle VirtualBox |
| Network Adapter | NAT Network |
| Target Domain | networkwalks.com |
| Terminal | Kali Linux Terminal |
| Assessment Tools | Six reconnaissance utilities |

## 4. Scope and Methodology

The assessment focuses on collecting and analysing publicly accessible information associated with the specified target domain.

The exercise follows a structured reconnaissance methodology consisting of six activities:

1. **Domain Registration Enumeration:** Investigating domain registration information, registrar details and authoritative name servers.
2. **Technology Fingerprinting:** Identifying technologies, web servers, content management systems and other components exposed by the website.
3. **DNS Resolution:** Determining the IP address associated with the target domain.
4. **HTTP Header Analysis:** Examining HTTP response headers to understand server responses and exposed configuration information.
5. **WAF Detection:** Investigating whether a Web Application Firewall is detected.
6. **DNS Enumeration:** Identifying publicly accessible DNS records, including name servers, mail servers and TXT records.

The assessment is limited to the reconnaissance activities specified in the practical instructions.

## 5. Tools and Techniques

### 5.1 WHOIS – Domain Registration Enumeration

**Purpose:**

WHOIS is a domain information lookup utility used to retrieve publicly available domain registration records.

It provides information that can help establish domain ownership records, registration history and DNS infrastructure.

**Command:**

```bash
whois networkwalks.com
```

**Information Investigated:**

- Domain registrar.
- Domain creation and expiry dates.
- Last updated date.
- Domain registration status.
- Authoritative name servers.
- Publicly available registration and administrative information.

**Security Relevance:**

WHOIS information can assist security professionals in understanding domain ownership records and identifying infrastructure relationships.

It can also provide useful background information during the initial reconnaissance phase of a security assessment.

### 5.2 WhatWeb – Website Technology Fingerprinting

### WhatWeb – Technology Fingerprinting

**Purpose:**

To identify the technologies and frameworks used by the target website through WhatWeb.

**Command:**

```bash
whatweb networkwalks.com
```

**Observation:**

The WhatWeb scan did not complete successfully. The tool remained in a loading state for an extended period before returning the following errors:

```text
ERROR Opening: http://networkwalks.com - execution expired
ERROR Opening: https://networkwalks.com - execution expired
```

**Result:**

Technology fingerprinting could not be completed using WhatWeb during this attempt. No technology identification results were obtained.

**Evidence:**

<img width="1910" height="966" alt="WhatWeb Scan Error" src="https://github.com/user-attachments/assets/41959640-b597-4239-9bad-2eb2f1aad9d8" />

**Troubleshooting:**

Further investigation is required to determine whether the issue is related to network connectivity, DNS resolution, server response time, or connection timeouts.
### 5.3 Nslookup – DNS Resolution

**Purpose:**

Nslookup is a network administration utility used to query DNS servers and retrieve information about domain names.

It helps establish the relationship between a domain name and its associated IP address.

**Command:**

```bash
nslookup networkwalks.com
```

**Information Investigated:**

- IPv4 addresses (A records).
- IPv6 addresses (AAAA records), where available.
- DNS server information.
- DNS query responses.

**Security Relevance:**

DNS resolution is an important part of reconnaissance because it helps identify the IP addresses associated with publicly accessible domain names.

This information provides a foundation for understanding an organisation's external network infrastructure.

### 5.4 cURL – HTTP Response Header Analysis

**Purpose:**

cURL is a command-line utility used to transfer data and communicate with servers using various network protocols, including HTTP and HTTPS.

In this exercise, it is used to retrieve HTTP response headers without downloading the complete webpage.

**Command:**

```bash
curl -I https://networkwalks.com
```

**Information Investigated:**

- HTTP response status codes.
- Server identification headers, where exposed.
- Content type.
- Cookies and session-related headers.
- Redirect information.
- Security-related HTTP headers.
- Other publicly exposed response information.

**Security Relevance:**

HTTP response headers can reveal information about a website's server configuration, application infrastructure and security settings.

Analysing these headers helps security professionals identify unnecessary information disclosure and potential configuration weaknesses.

### 5.5 Wafw00f – Web Application Firewall Detection

**Purpose:**

Wafw00f is a security reconnaissance utility designed to identify Web Application Firewalls protecting websites.

It analyses HTTP responses and uses detection techniques to identify known WAF technologies.

**Command:**

```bash
wafw00f networkwalks.com
```

**Information Investigated:**

- Whether a WAF is detected.
- The identified WAF vendor, where possible.
- Detection responses and supporting information.

**Security Relevance:**

A Web Application Firewall helps protect web applications by monitoring and filtering HTTP traffic.

Identifying WAF technologies provides security professionals with information about the defensive mechanisms protecting an application.

However, detecting a WAF does not automatically establish whether a website is secure or vulnerable.

### 5.6 DNSRecon – DNS Enumeration

**Purpose:**

DNSRecon is a DNS enumeration tool used to gather information about DNS infrastructure associated with a domain.

It helps identify publicly available DNS records and other relevant infrastructure information.

**Command:**

```bash
dnsrecon -d networkwalks.com
```

**Information Investigated:**

- A records.
- AAAA records.
- Name Server (NS) records.
- Mail Exchange (MX) records.
- Text (TXT) records.
- Sender Policy Framework (SPF) information.
- Service (SRV) records, where available.
- Other publicly discoverable DNS information.

**Security Relevance:**

DNS enumeration provides insight into an organisation's domain infrastructure, including its email services, name servers and publicly exposed services.

Security professionals use this information to understand the external attack surface and identify areas that may require further security review.

## 6. Security Implications

Footprinting and reconnaissance can reveal valuable information about an organisation's publicly exposed infrastructure.

Although the tools used in this exercise primarily collect information rather than exploit vulnerabilities, their findings can help establish an understanding of an organisation's external attack surface.

The information collected may reveal:

- Domain registration and ownership records.
- Hosting and DNS infrastructure.
- Publicly exposed web technologies and software versions.
- IP addresses associated with domain names.
- Web server response information.
- Web Application Firewall technologies.
- Email and DNS service configurations.

Organisations should regularly review their publicly exposed information, maintain updated software and implement appropriate security configurations to reduce unnecessary information disclosure.

## 7. Challenges Encountered

During the practical exercise, technical challenges were encountered while executing some of the reconnaissance tools.

One of the challenges involved WhatWeb, which returned connection timeout errors when attempting to access both the HTTP and HTTPS versions of the target website.

This required further consideration of possible connectivity, DNS resolution and HTTP response issues.

The experience highlighted the importance of troubleshooting network communication and understanding tool behaviour when conducting reconnaissance.

Other observations and challenges encountered during the practical activities are documented in the supporting evidence.

## 8. Conclusion

This practical exercise provided hands-on exposure to footprinting and reconnaissance using six different tools available in Kali Linux.

By investigating domain registration information, website technologies, DNS records, HTTP response headers and Web Application Firewall detection, the exercise demonstrated how publicly accessible information can be collected and analysed to understand a website's external infrastructure.

It strengthened my understanding of important networking and cybersecurity concepts, including DNS, HTTP communication, domain registration, web technologies and web application security.

The exercise also demonstrated the importance of selecting appropriate reconnaissance tools, interpreting their outputs and troubleshooting unexpected results.

The knowledge gained provides a foundation for further learning and practical activities in ethical hacking and cybersecurity.

## 10. Evidence and Screenshots

This section contains screenshots captured during the practical execution of the six reconnaissance activities.

The screenshots serve as supporting evidence of the commands executed and the results obtained during the assessment.

### 10.1 WHOIS – Domain Registration Information

**Evidence:** <img width="1917" height="987" alt="whois1" src="https://github.com/user-attachments/assets/85946755-3304-4d26-9d47-fe07bf28882d" />


This screenshot demonstrates the execution of WHOIS and the retrieval of publicly available domain registration information.

### 10.2 Nslookup – DNS Resolution

**Evidence:** <img width="1890" height="945" alt="nslookup" src="https://github.com/user-attachments/assets/52add7eb-064d-48a1-baeb-7d44ba0c0676" />


This screenshot demonstrates the DNS resolution process used to identify the IP address associated with the target domain.

### 10.3 cURL – HTTP Response Header Analysis

**Evidence:** <img width="1907" height="960" alt="curl" src="https://github.com/user-attachments/assets/b8511c05-27e3-41e0-9c87-b149fd790d18" />

This screenshot demonstrates the retrieval and inspection of HTTP response headers from the target website.

### 10.4 Wafw00f – Web Application Firewall Detection

**Evidence:** <img width="1907" height="970" alt="wafw00f" src="https://github.com/user-attachments/assets/cb6b8522-cb9a-4940-b174-d4d9eff40dd9" />


This screenshot demonstrates the use of Wafw00f to investigate whether a Web Application Firewall is detected.

### 10.5 DNSRecon – DNS Enumeration

**Evidence:** <img width="1896" height="950" alt="dnsrecon" src="https://github.com/user-attachments/assets/169dd152-a89a-4126-9823-375e3aabfe02" />


This screenshot demonstrates the execution of DNSRecon to enumerate publicly available DNS records associated with the target domain.
