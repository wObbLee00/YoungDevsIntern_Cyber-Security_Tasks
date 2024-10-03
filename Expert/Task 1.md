### **Step 1: Setting Up Burp Suite**
1. **Launch**:
   - Launch the community free edition of Burp Suite.

2. **Configure Your Browser**:
   - In Burp Suite, go to **Proxy > Intercept** and ensure "Intercept is off."
   - **Set your browser to use Burp's proxy** (default: `127.0.0.1:8080`):
     - In your browser's **Network Settings**, set manual proxy configuration to `127.0.0.1` for HTTP/HTTPS with port `8080`.

3. **Install Burp's CA Certificate**:
   - Open your browser and visit `http://burp` while Burp Suite is running.
   - Download and install the CA certificate for analyzing HTTPS traffic.

---

### **Step 2: Scanning for Vulnerabilities**
1. **Manual Testing with Proxy**:
   - Ensure **Intercept** is off in **Proxy**.
   - Visit key pages of the web app (e.g., login forms) and enter test data.
   - View requests and responses between your browser and the web app in **Proxy > HTTP history**.

2. **Automated Scanning**:
   - In **Target > Site Map**, right-click the target domain and select **Scan**.
   - Choose specific sections (like login pages or forms) for active scanning, checking for vulnerabilities such as SQL Injection and Cross-Site Scripting (XSS).

---

### **Step 4: Intercepting and Modifying Requests**
1. **Intercepting**:
   - Turn **Intercept on** in **Proxy > Intercept**.
   - Perform an action in the web app (e.g., submit a form). The HTTP request will appear in Burp's **Intercept** tab.

2. **Modifying Requests**:
   - You can edit the parameters in the request before forwarding it to the server.
   - Example: Modify the parameter to `' OR 1=1--` to test for SQL Injection and forward the request.
   - Observe the response from the server to identify potential vulnerabilities.

---

### **Step 5: Testing for Vulnerabilities**
1. **SQL Injection**:
   - Use **Proxy > Intercept** or **Repeater** (explained later) to modify input fields or URL parameters (e.g., entering `' OR 1=1--` in a login form) and test for SQL Injection.

2. **Cross-Site Scripting (XSS)**:
   - Inject script tags (e.g., `<script>alert('XSS')</script>`) into input fields.
   - If the script runs in the browser, the application is vulnerable to XSS.

3. **Cross-Site Request Forgery (CSRF)**:
   - Use **Repeater** to craft and send requests without proper CSRF tokens to test if the app lacks protection against unauthorized actions.

---

### **Step 6: Using Repeater to Repeat and Modify Requests**
1. **Send Request to Repeater**:
   - In **Proxy > HTTP history**, right-click the request you want to repeat and modify, then select **Send to Repeater**.

2. **Modify and Resend**:
   - Go to the **Repeater** tab. Modify the request (parameters, headers) and click **Send**.
   - Check the server's response to see if the changes reveal vulnerabilities like SQL Injection or XSS.

---

### **Step 7: Reporting and Remediation**
After identifying vulnerabilities, document them in a report with these sections:
   - **Vulnerability description**: What you found (e.g., SQL Injection).
   - **Affected pages**: URLs and pages impacted.
   - **Proof of concept**: Show how the vulnerability can be exploited.
   - **Remediation steps**: Suggestions to fix the issue (e.g., input validation, secure headers).

---

### **Example Walkthrough**

#### **1. Intercepting a Login Form**:
   - Visit the web app's login page.
   - Turn on **Intercept** in **Proxy** and submit the login form.
   - Modify the username parameter (e.g., `admin' OR 1=1--`) to test for SQL Injection.
   - Forward the request and check if you're logged in without a valid password.

#### **2. Testing for XSS**:
   - Use the search or input form in the web app.
   - Inject `<script>alert('XSS')</script>` into the field.
   - If the app executes the script in the browser, it's vulnerable to XSS.
