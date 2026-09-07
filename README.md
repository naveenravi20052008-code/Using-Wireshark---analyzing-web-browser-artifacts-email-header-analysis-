# Using-Wireshark---analyzing-web-browser-artifacts-email-header-analysis
## AIM:
To use Wireshark to analyze web browser activities and inspect email headers from captured network traffic.
## Architecture Diagram:
```mermaid
flowchart TD
    A[User System] --> B[Web Browser]
    A --> C[Email Client]
    B --> D[Network Traffic]
    C --> D
    D --> E[Wireshark Capture Engine]
    E --> F[Protocol Decoders HTTP SMTP IMAP POP]
    F --> G[Browser Artifacts URLs Cookies Auth]
    F --> H[Email Headers Source IP Server Timestamps]
    G --> I[Findings and Reports]
    H --> I
```
## DESIGN STEPS:
### Step 1:
- Install Wireshark and ensure correct network adapter selection.
- Enable packet capturing for your active interface (Wi-Fi/Ethernet).

### Step 2:
**Web Browser Artifact Analysis**
- Open a browser and visit websites with login forms (use dummy credentials).
- In Wireshark, filter traffic with:
    - ```http``` for normal HTTP requests
    - ```http.cookie``` for cookies
    - ```http.authbasic``` for basic authentication
- Identify:
    - URLs visited
    - GET/POST requests
    - Cookies & session IDs
    - Credentials (if plaintext HTTP is used)
### Step 3:
- Capture email traffic by sending/receiving emails (dummy mail server or provided PCAP).
- Use filters:
    - ```smtp``` (Simple Mail Transfer Protocol)
    - ```pop``` / ```imap``` (for received mail)
- Inspect email headers:
    - Source IP
    - Mail server hostname
    - Timestamps
    - Possible forged headers
## PROGRAM:
```mermaid
flowchart TD
    A[Start Wireshark Capture] --> B[Generate Traffic: Web Browsing & Emails]
    B --> C[Apply Protocol Filters: HTTP/SMTP/IMAP/POP]
    C --> D[Extract Browser Artifacts: URLs, Cookies, Credentials]
    C --> E[Analyze Email Headers: Source, Server, Metadata]
    D --> F[Save Findings]
    E --> F[Save Findings]
    F --> G[Generate Digital Forensic Report]
```

## OUTPUT:
Captured Web Activity and Email Header Information
<img width="1617" height="861" alt="Screenshot 2026-09-07 173313" src="https://github.com/user-attachments/assets/76ed29c1-0f99-45ea-a1b5-72c673d0ccd3" />

<img width="1200" height="587" alt="Screenshot 2026-09-07 173342" src="https://github.com/user-attachments/assets/116452e9-cba4-4504-bfba-fd63064410b9" />


<img width="812" height="417" alt="Screenshot 2026-09-07 173731" src="https://github.com/user-attachments/assets/05556a35-1b20-4e27-b659-c5f1d2faf14a" />

<img width="642" height="347" alt="Screenshot 2026-09-07 173635" src="https://github.com/user-attachments/assets/6d2675e2-c11c-46a6-8bdb-368b4e007dc6" />

<img width="808" height="421" alt="Screenshot 2026-09-07 174158" src="https://github.com/user-attachments/assets/48b02450-fd58-4530-836d-2b4bfeeb4d2d" />

<img width="952" height="487" alt="Screenshot 2026-09-07 173859" src="https://github.com/user-attachments/assets/9d672d7c-084f-4c3f-b750-bca2999c1606" />

<img width="961" height="506" alt="Screenshot 2026-09-07 174146" src="https://github.com/user-attachments/assets/b8740d7a-2c61-49b8-b5c8-6b4860e6fcaf" />

## RESULT:
Web browser artifacts and email headers were successfully analyzed using Wireshark.

