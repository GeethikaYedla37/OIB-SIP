# Vulnerability Scanning with Nikto

## Objective

To perform a basic vulnerability scan on a target web server using **Nikto**, identify common security misconfigurations, and document the findings for awareness and remediation.

---

## Tools Used

- **Nikto v2.5.0**
- **Operating System**: Kali Linux
- **Target**: `http://testphp.vulnweb.com`

---

## Steps Performed

### 1. Install Nikto

Nikto comes pre-installed on Kali Linux. If not, it can be installed using:
```bash
sudo apt install nikto -y
```
### 2. Run the Scan
Executed the scan with output saved to a text file:
```
nikto -h http://testphp.vulnweb.com -o nikto_scan_results.txt
```
### 3. Analyze Results
- Target IP:          44.228.249.3
- Target Hostname:    testphp.vulnweb.com
- Target Port:        80
- Server:             nginx/1.19.0

/login.php: The anti-clickjacking X-Frame-Options header is not present.
/login.php: The X-Content-Type-Options header is not set.
/php5.6.X67ErH.php: Retrieved x-powered-by header: PHP/5.6.40-38+ubuntu20.04.1+deb.sury.org+1


## Vulnerabilities Identified
| Vulnerability                    | Description                                                                                  | Risk          |
| -------------------------------- | -------------------------------------------------------------------------------------------- | ------------- |
| Missing X-Frame-Options          | Site is vulnerable to clickjacking attacks.                                                  | Medium        |
| Missing X-Content-Type-Options   | May allow MIME-type confusion attacks.                                                       | Medium        |
| X-Powered-By Header Disclosure   | Reveals server technology (PHP version) — useful to attackers for version-specific exploits. | Low           |
| HTTP 500 Error on some resources | Indicates improper input handling or server misconfigurations.                               | Informational |

