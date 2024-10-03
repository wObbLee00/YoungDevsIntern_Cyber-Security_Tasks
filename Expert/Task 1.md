### **Step 1: Setting Up Burp Suite**
1. **Launch**:
   - Launch the community free edition of Burp Suite.
   - ![Step1](https://github.com/user-attachments/assets/b02e404a-78f6-4a58-bfd4-9fe15f0c355b)


2. **Configure Your Browser**:
   - In Burp Suite, go to **Proxy > Intercept** and ensure "Intercept is off."
   - **Set your browser to use Burp's proxy** (default: `127.0.0.1:8080`):
     - In your browser's **Network Settings**, set manual proxy configuration to `127.0.0.1` for HTTP/HTTPS with port `8080`.
   ![Step2](https://github.com/user-attachments/assets/727f589b-247a-45b1-98ff-6b01c1f97bd1)


3. **Install Burp's CA Certificate**:
   - Open your browser and visit `http://burp` while Burp Suite is running.
   - Download and install the CA certificate for analyzing HTTPS traffic.
   - ![Step4](https://github.com/user-attachments/assets/c2eee371-262c-4b38-bd73-73b4ed3217ab)

---

### **Step 2: Scanning for Vulnerabilities**
1. **Manual Testing with Proxy**:
   - Ensure **Intercept** is off in **Proxy**.
   - Visit key pages of the web app (e.g., login forms) and enter test data.
   - ![Step9](https://github.com/user-attachments/assets/61810e8b-1f59-41f5-8d1d-2d5706ab2709)
   - View requests and responses between your browser and the web app in **Proxy > HTTP history**.
   - 

2. **Automated Scanning**:
   - In **Target > Site Map**, right-click the target domain and select **Scan**.
   - Choose specific sections (like login pages or forms) for active scanning, checking for vulnerabilities such as SQL Injection and Cross-Site Scripting (XSS).

---

### **Step 4: Intercepting and Modifying Requests**
1. **Intercepting**:
   - Turn **Intercept on** in **Proxy > Intercept**.
   - Perform an action in the web app (e.g., submit a form). The HTTP request will appear in Burp's **Intercept** tab.
   - ![Step11](https://github.com/user-attachments/assets/10ea7d13-9a57-413b-9fa5-26db2c7ffd05)


2. **Modifying Requests**:
   - You can edit the parameters in the request before forwarding it to the server.
   - Example: Modify the parameter to `' OR 1=1--` to test for SQL Injection and forward the request.
   - Observe the response from the server to identify potential vulnerabilities.
   - ![Step12](https://github.com/user-attachments/assets/da331bc0-702b-47a2-9d49-cb70619914bc)

---

### **Step 5: Testing for Vulnerabilities**
1. **SQL Injection**:
   - Use **Proxy > Intercept** or **Repeater** (explained later) to modify input fields or URL parameters (e.g., entering `' OR 1=1--` in a login form) and test for SQL Injection.

2. **Cross-Site Scripting (XSS)**:
   - Inject script tags (e.g., `<script>alert('XSS')</script>`) into input fields.
   - If the script runs in the browser, the application is vulnerable to XSS.

3. **Cross-Site Request Forgery (CSRF)**:
   - Use **Repeater** to craft and send requests without proper CSRF tokens to test if the app lacks protection against unauthorized actions.
### **Step 7: Conclusion**
After testing the Facebook login page using Burp Suite, no vulnerabilities were found. This outcome suggests that Facebook has implemented strong security measures to protect against common web vulnerabilities like SQL Injection, Cross-Site Scripting (XSS), and others.
