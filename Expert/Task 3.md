## Task 3: Secure a Web Application

### Step 1: Deploy a Simple Website on GitHub

1. **Create an HTML File**:
   - Create a simple HTML file.
   - ![Step 0](https://github.com/user-attachments/assets/9ce3304b-5a8c-4bc1-9795-5fdc82884d2a)



2. **Upload the HTML File to GitHub**:
   - Go to your GitHub account and create a new repository (e.g., `secure-web-app`).
   - Upload the `index.html` file to the repository.
   - ![Step1](https://github.com/user-attachments/assets/2f208c99-8ea5-4c40-8cde-8b86cbda7445)
   - Enable GitHub Pages in the repository settings to host your website.
   - ![Step2](https://github.com/user-attachments/assets/75ad45b8-2867-4157-9fba-6534d9c47a7b)


### Step 2: Apply Security Headers

#### 2.1 Content Security Policy (CSP)
- **Overview**: CSP is a security feature that helps prevent various attacks, including Cross-Site Scripting (XSS) and data injection attacks.
- **Implementation**: To apply CSP, add the following HTTP header to your web server configuration:
  ```
  Content-Security-Policy: default-src 'self'; script-src 'self'; object-src 'none';
  ```

#### 2.2 HTTP Strict Transport Security (HSTS)
- **Overview**: HSTS is a web security policy mechanism that helps protect websites against man-in-the-middle attacks such as protocol downgrades.
- **Implementation**: To enable HSTS, add the following header:
  ```
  Strict-Transport-Security: max-age=31536000; includeSubDomains
  ```
  ![Step3](https://github.com/user-attachments/assets/c9715982-f4da-4145-a9b4-edacd76a3ee0)


### Step 3: Conduct a Thorough Review of Code for Common Vulnerabilities

#### 3.1 Review for SQL Injection Vulnerabilities
1. **Understand SQL Injection**:
   - SQL injection occurs when an attacker manipulates SQL queries by injecting malicious SQL code into input fields.

2. **Identify User Input Points**:
   - Look for places in the code where user input is processed (e.g., login forms, search bars).

3. **Check for Dynamic SQL Queries**:
   - Review the code for any dynamic SQL queries that concatenate user input directly into the query string.

4. **Mitigation Techniques**:
   - **Use Prepared Statements**: Ensure the application uses prepared statements or parameterized queries to prevent SQL injection.
   - **Input Validation**: Validate user input by using whitelisting techniques to accept only expected characters.

#### 3.2 Review for Cross-Site Scripting (XSS) Vulnerabilities
1. **Understand XSS**:
   - XSS vulnerabilities occur when an attacker injects malicious scripts into web pages viewed by other users.

2. **Identify Output Points**:
   - Review the code for areas where user input is rendered on web pages.

3. **Check for Unsafe Output Encoding**:
   - Look for code that outputs user input without proper encoding.

4. **Mitigation Techniques**:
   - **Output Encoding**: Ensure that user input is properly encoded before rendering.
   - **Use CSP**: Implement a Content Security Policy to restrict which scripts can be executed on your web pages.

### Step 4: Code Review Checklist
- **For SQL Injection**:
  - [ ] Are all user inputs validated?
  - [ ] Are prepared statements or parameterized queries used for database interactions?
  - [ ] Are database queries logged and monitored for suspicious activities?

- **For XSS**:
  - [ ] Is user-generated content properly encoded before being displayed on the page?
  - [ ] Are there any functions that directly manipulate the DOM without encoding?
  - [ ] Is a Content Security Policy (CSP) in place to limit the execution of scripts?

### Conclusion
Implementing advanced security measures such as CSP and HSTS, along with conducting a thorough code review for common vulnerabilities, is essential for securing web applications. By following best practices for input validation, output encoding, and using prepared statements, developers can significantly reduce the risk of exploitation. Regular security assessments should be an integral part of the development process.
