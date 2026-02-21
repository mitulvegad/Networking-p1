# 🌐 Networking

Welcome to the **Networking** deep-dive module. This section is designed to transform your understanding of how data travels across the globe, from physical electrical signals to complex logical routing and application delivery.

(https://capsule-render.vercel.app/render?type=waving&color=auto&height=200&section=header&text=Networking%20Deep%20Dive&fontSize=50)

<h2>Osi Model</h2>

The **Open Systems Interconnection (OSI)** model is a conceptual framework that standardizes the functions of a telecommunication or computing system into seven distinct layers.



* **Layer 7 - Application:** The interface where users interact with the network (HTTP, FTP, SSH).
* **Layer 6 - Presentation:** Handles data formatting, encryption, and compression (SSL/TLS, JPEG).
* **Layer 5 - Session:** Manages sessions between applications. It handles **Checkpoints** to ensure that if a connection drops, it can resume from the last known state.
* **Layer 4 - Transport:** Manages end-to-end communication. It is responsible for **Segmentation** (breaking data into smaller pieces) and **Flow Control**.
* **Layer 3 - Network:** Responsible for logical addressing and routing. This is where the "best path" for a packet is determined.
* **Layer 2 - Data Link:** Handles physical addressing (MAC addresses). It is split into two sub-layers: **LLC** (Logical Link Control) and **MAC** (Media Access Control).
* **Layer 1 - Physical:** The actual hardware—cables, radio waves, and the transmission of raw bits (0s and 1s).

---

<h2>Tp (transmission Protocols & Twisted Pair)</h2>

Networking relies on both physical media and logical rules to ensure data integrity.

### **Transmission Protocols**
* **TCP (Transmission Control Protocol):** Connection-oriented. It ensures 100% data delivery through error-checking and sequencing.
* **UDP (User Datagram Protocol):** Connectionless. It is a "fire and forget" protocol used when speed is more important than reliability (e.g., VoIP, Streaming).

### **Twisted Pair (Cables)**
Copper cabling is the backbone of most LANs.
* **UTP (Unshielded Twisted Pair):** Cost-effective but susceptible to EMI (Electromagnetic Interference).
* **STP (Shielded Twisted Pair):** Includes a foil shield to protect data in environments with heavy machinery or electrical noise.
* **Categories:**
    * **Cat5e:** Up to 1 Gbps (100 MHz).
    * **Cat6:** Up to 10 Gbps (250 MHz) for short distances.
    * **Cat6a:** Up to 10 Gbps (500 MHz) with better shielding.



---

<h2>Ip Addressing</h2>

An **IP Address** is a logical address used to locate a device on a network.

* **IPv4:** A 32-bit numeric address (e.g., `172.16.254.1`). It has a limit of roughly **4.3 billion** addresses.
* **IPv6:** A 128-bit hexadecimal address (e.g., `2001:0db8:85a3:0000:0000:8a2e:0370:7334`) designed to replace IPv4.
* **Special Addresses:**
    * **Loopback (localhost):** `127.0.0.1` (Used for testing your own machine).
    * **APIPA:** `169.254.x.x` (Assigned automatically when a DHCP server isn't found).

---

<h2>Subnetting</h2>

Subnetting is the mathematical process of dividing a large network into smaller, manageable pieces to reduce "Broadcast Storms" and increase security.

* **Subnet Mask:** A filter that tells the computer which part of the address belongs to the network and which to the host.
* **CIDR (Classless Inter-Domain Routing):** Shorthand notation (e.g., `/24`).
* **The Math:** To find the number of usable hosts in a subnet, use the formula:
    $$2^{(32 - n)} - 2$$
    *(We subtract 2 because the first address is the **Network ID** and the last address is the **Broadcast ID**.)*



---

<h2>Layer3-Layer5 (deep Learning)</h2>

### **Layer 3: The Network Layer (Deep)**
This is where **Routers** live. They use a **Routing Table** to make decisions based on the destination IP.
* **TTL (Time to Live):** A value that decreases at every hop. If it hits 0, the packet is dropped to prevent infinite loops.
* **ICMP:** The protocol used by `ping` and `traceroute` to diagnose network health.

### **Layer 4: The Transport Layer (Deep)**
This layer uses **Ports** (0 to 65535) to direct traffic to specific applications.
* **TCP 3-Way Handshake:**
    1.  **SYN** (Synchronize)
    2.  **SYN-ACK** (Synchronize-Acknowledge)
    3.  **ACK** (Acknowledge)



### **Layer 5: The Session Layer (Deep)**
Layer 5 keeps different "conversations" separate. If you have multiple browser tabs open, the Session Layer ensures the data for one site doesn't end up in another tab.

---

<h2>What Is A Class</h2>

Historically, IPv4 was divided into classes to help with allocation:

| Class | First Octet Range | Default Mask | Use Case |
| :--- | :--- | :--- | :--- |
| **A** | 1 - 126 | `255.0.0.0` | Massive Organizations |
| **B** | 128 - 191 | `255.255.0.0` | Medium to Large Networks |
| **C** | 192 - 223 | `255.255.255.0` | Small Local Networks (Home) |
| **D** | 224 - 239 | N/A | Multicasting |
| **E** | 240 - 255 | N/A | Research/Experimental |

---

<h2>Private Ip Vs Public Ip</h2>

* **Public IP:** The address assigned to your router by your ISP. It is visible to the entire world.
* **Private IP:** Used inside your home/office. These are "non-routable" on the internet.
* **NAT (Network Address Translation):** A service on your router that translates your many private IPs into one single public IP.
* **PAT (Port Address Translation):** A specific type of NAT that uses port numbers to track which internal device requested which external data.

---

<h2>Common Ports & Common Services</h2>

Ports act as "doors" to your computer. Knowing common ports is essential for security and administration.

| Service | Port | Protocol | Description |
| :--- | :--- | :--- | :--- |
| **FTP** | 21 | TCP | File Transfer |
| **SSH** | 22 | TCP | Secure Remote Login |
| **DNS** | 53 | UDP/TCP | Domain Name Resolution |
| **HTTP** | 80 | TCP | Unencrypted Web Traffic |
| **HTTPS** | 443 | TCP | Encrypted Web (SSL/TLS) |
| **RDP** | 3389 | TCP | Remote Desktop |
| **MySQL** | 3306 | TCP | Database Service |

---

<h2>How Ip's Assign (dhcp & Dns)</h2>

### **DHCP (Dynamic Host Configuration Protocol)**
Automatically assigns IP addresses, Gateway, and DNS settings to devices on the network.
* **DORA Process:**
    1.  **D**iscover (Client: "Who is the server?")
    2.  **O**ffer (Server: "I have this IP for you.")
    3.  **R**equest (Client: "I'll take it!")
    4.  **A**cknowledge (Server: "Confirmed. It's yours.")



### **DNS (Domain Name System)**
Translates domain names (google.com) into IP addresses (8.8.8.8).
* **Records to Know:**
    * **A Record:** Maps a name to an IPv4 address.
    * **AAAA Record:** Maps a name to an IPv6 address.
    * **MX Record:** Directs email traffic to the mail server.
    * **CNAME:** An alias for another name.

---

<h2>📺 Learning Resource Recommendation</h2>

For a professional-grade understanding of these protocols, I highly recommend following:

### **[Bitten Tech YouTube Channel](https://www.youtube.com/@BittenTech)**
**Bitten Tech** provides excellent deep-dive courses that break down these complex protocols into easy-to-understand modules, explaining the "how" and "why" behind every packet.

---

<img src="https://user-images.githubusercontent.com/74038190/235224431-e8c8c12e-6826-47f1-89fb-2ddad83b3abf.gif" width="300">&nbsp;&nbsp;<img src="https://user-images.githubusercontent.com/74038190/225813708-98b745f2-7d22-48cf-9150-083f1b00d6c9.gif" width="500">
<br><br>
