# Network Traffic Analysis Report

## Overview
This report documents an analysis of a captured network session using Wireshark. The capture demonstrates how key protocols — TCP, DNS, HTTP, and TLS — operate at different stages of a network transaction.

---

## Capture Summary
- **File**: `googletest.pcapng`
- **Method**: Captured using Wireshark on macOS
- **Duration**: Short active browsing session
- **Extracted Stream**: `followed_stream_1.txt`

---

## Key Observations

### 1. TCP Handshake
- Captured typical 3-way handshake (`SYN`, `SYN-ACK`, `ACK`) initiating TCP communication.
- Confirms reliable transport-layer connection setup.

### 2. DNS Resolution
- Standard DNS query for resolving a hostname.
- Response includes IPv4 address of the requested domain.

### 3. TLS Handshake (HTTPS)
- Client Hello and Server Hello messages captured.
- Cipher suite negotiation and certificate exchange indicate start of encrypted HTTPS session.

### 4. Followed TCP Stream
- File: `googletest_TCPstream.pcapng`
- Contains extracted HTTP traffic from a selected TCP conversation.
- Shows readable request headers, e.g., `GET / HTTP/1.1`, `Host:`, `User-Agent`.

---

## Conclusion
This simple network analysis highlights how common protocols interact in a basic browsing session. By following a single TCP stream, we isolate a specific conversation for deeper inspection — a powerful technique when analyzing large capture files.

---

## Recommendations for Future Work
- Use display filters to isolate traffic types automatically.
- Apply decryption keys (if available) to analyze HTTPS content.
- Track user behavior across multiple conversations using flow tools.
