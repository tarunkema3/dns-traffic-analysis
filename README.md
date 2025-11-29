# 🛰️ DNS Traffic Analysis using Wireshark

## 📌 Project Overview
This project demonstrates practical DNS traffic capture and analysis performed using Wireshark.  
I inspected live DNS packets generated while accessing `www.wikipedia.org`, analyzed AAAA IPv6 responses, evaluated CNAME redirections, and identified my DNS resolver.  

This project highlights my foundational skills for roles such as:
- SOC Analyst (Tier 1)  
- Network Security Engineer  
- Cybersecurity Analyst  

---

## 🎯 Objectives
- Capture real DNS traffic  
- Apply Wireshark display filters  
- Inspect DNS query/response packets  
- Analyze IPv6 (AAAA) and CNAME records  
- Extract DNS resolver details  
- Document findings professionally  

---

## 🛠 Tools Used
- **Wireshark**
- **Browser (traffic generation)**
- **Windows 11 / IPv6-enabled network**

---

# 🔎 Procedure & Analysis

## 1️⃣ Start Wireshark Capture
I selected my active Wi-Fi interface and filtered DNS traffic using:


### 📷 Screenshot: DNS Filter Applied  
[image alt](https://github.com/tarunkema3/dns-traffic-analysis/blob/c39fb7ca3a4b2b0d52e7db258d5de8c681a62e59/Screenshot.dns-filter-version.png)

This screenshot shows:
- Clean DNS-only packet view  
- Multiple DNS responses from Wikipedia and Google  
- AAAA IPv6 records  
- CNAME redirection entries  

---

## 2️⃣ DNS Response Packet (IPv6 Address Returned)

The DNS response returned Wikipedia’s IPv6 address:


### 📷 Screenshot: IPv6 DNS Response Packet  
![IPv6 DNS Response](screenshots/dns-ipv6-response.png)

Visible in this screenshot:
- **Source Address:** DNS resolver  
- **Destination Address:** My device  
- Protocol: UDP (port 53)  
- IPv6 response content  

---

## 3️⃣ Detailed Packet Structure (Hex + ASCII View)

I inspected the packet contents across all protocol layers:
- Ethernet II  
- IPv6  
- UDP  
- DNS  

### 📷 Screenshot: DNS Packet Hex Breakdown  
![DNS Packet Breakdown](screenshots/dns-packet-expanded.png)

This view shows:
- Transaction ID  
- Flags  
- Query/answer sections  
- Hex/ASCII domain representation  

---

## 4️⃣ DNS Resolver IP Identified

DNS traffic was answered by my local IPv6 DNS resolver:


### 📷 Screenshot: DNS Resolver Packet  
![DNS Resolver Packet](screenshots/dns-resolver-ip.png)

Details shown:
- Incoming DNS response from port 53  
- Resolver’s IPv6 address  
- Successful `Standard query response` flag  

---

## 5️⃣ DNS Record Type Analysis (CNAME)

Wikipedia’s domain redirected using a CNAME record:  

### 📷 Screenshot: DNS Record Type (CNAME)  
![DNS Record Type](screenshots/dns-record-type.png)

This screenshot confirms:
- Query type = HTTPS  
- Answer = **CNAME**  
- Authoritative nameservers listed  

---

# 📊 Findings Summary

### ✔ IPv6 AAAA Records
Captured and validated IPv6 DNS responses.

### ✔ CNAME Redirection
Observed typical CDN-style domain redirection used by Wikipedia.

### ✔ DNS Resolver Identified
Extracted resolver IP used by my system.

### ✔ Full Packet-Layer Analysis
Reviewed DNS packets at Network, Transport, and Application layers.

---

# 🧩 Skills Demonstrated
- Wireshark packet capture  
- DNS & UDP protocol analysis  
- Filtering and traffic isolation  
- IPv6 and AAAA record interpretation  
- CNAME and domain resolution understanding  
- SOC-style analytical documentation  
