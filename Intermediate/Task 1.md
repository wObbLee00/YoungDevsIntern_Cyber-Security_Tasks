### Task 1: Basic Vulnerability Scan Using Nmap

#### Overview
In this task, I performed a basic vulnerability scan on the target IP `192.168.x.x` using **Nmap**, an open-source network scanning tool. The goal was to identify open ports, detect service versions, and check for vulnerabilities.

#### Steps

1. **Installing Nmap**  
   First, I made sure that **Nmap** was installed in my Kali Linux environment. I used the following command to install Nmap:
   ![Step 1](https://github.com/user-attachments/assets/207936ee-8bff-4c2a-bc48-875d801ac954)

3. **Basic Scan of the Target**  
   I initiated a basic scan of the target IP address to check for open ports and services:
   ![Step 2](https://github.com/user-attachments/assets/23b46f69-c196-4a6f-b883-2a767cf3ffdd)

   This command provided an overview of open ports and services running on the target machine.

4. **Service Version Detection**  
   To gather more details about the services running on the open ports, I used the `-sV` flag to detect service versions:
   ![Step 3](https://github.com/user-attachments/assets/ad4f7fee-48c6-4d4d-af00-4dd1846b3b6b)

   This step allowed me to identify the specific versions of the services, which could be crucial for identifying vulnerabilities.

5. **Vulnerability Scan**  
   Finally, I performed a vulnerability scan using the Nmap **vuln** script:
   ![Step 4](https://github.com/user-attachments/assets/d78facf3-44f2-44d5-982d-543670c23aac)

   This script identifies known vulnerabilities in the services running on the target.
