# Basic Firewall Configuration with UFW

## Objective

To configure a basic firewall on a Linux system using **UFW (Uncomplicated Firewall)**. The task focuses on allowing secure remote access via **SSH** while denying unencrypted **HTTP** traffic. This demonstrates fundamental firewall setup and hardening techniques.

---

## 🛠️ Tools Used

- **UFW (Uncomplicated Firewall)**
- **Operating System**: Kali Linux / Ubuntu-based system
- **Terminal (CLI)**

---

## Configuration Steps

### 1. Install UFW

Install UFW using the package manager:

```bash
sudo apt update
sudo apt install ufw -y
```
### 2. Enable the Firewall
Activate UFW so it begins enforcing rules:

```bash
sudo ufw enable
```
### 3. Allow SSH (Port 22)
Allow incoming SSH connections to ensure remote login is not blocked:

```bash
sudo ufw allow ssh
OR
sudo ufw allow 22/tcp
```
### 4. Deny HTTP (Port 80)
Block HTTP traffic, which uses port 80, to prevent unencrypted web access:

```bash
sudo ufw deny http
OR
sudo ufw deny 80/tcp
```
### 5. Check UFW Status
Verify that the rules are active and correct:
``` 
sudo ufw status verbose
```
### Expected Output:
Status: active
To                         Action      From
--                         ------      ----
22/tcp                     ALLOW       Anywhere
80/tcp                     DENY        Anywhere
22/tcp (v6)                ALLOW       Anywhere (v6)
80/tcp (v6)                DENY        Anywhere (v6)
