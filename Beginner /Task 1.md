# Task 1: Set Up Basic Firewall Rules

### Objective
To configure and create custom firewall rules using Windows Defender Firewall to control incoming connections on the system.

### Steps

1. **Open Windows Defender Firewall Settings**:
   - Navigate to the **Control Panel**.
   - ![Step 1](https://github.com/user-attachments/assets/0ff73789-e6ce-491a-b247-9a47af582546)
   - Select **Security and Maintenance**.
   - ![Step 2](https://github.com/user-attachments/assets/58346356-9e8b-494f-a300-b7f73cc40c39)
   - From there, click on **Windows Defender Firewall**.
   - ![Step 3](https://github.com/user-attachments/assets/b2a54a97-5d64-4e75-a4e8-dd10f216014c)

2. **Access Advanced Firewall Settings**:
   - In the Windows Defender Firewall window, click on **Advanced Settings** located on the left-hand side. This will open the **Windows Defender Firewall with Advanced Security** console.
   - ![Step 4](https://github.com/user-attachments/assets/82889c61-3ed2-4350-8645-947518347e65)

3. **Create a New Inbound Rule**:
   - In the Advanced Security console, click on **Inbound Rules** in the left-hand panel.
   - Select **New Rule** from the right-hand panel to begin creating a new inbound rule.

4. **Choose Rule Type**:
   - You will be prompted to select the type of rule you want to create. Options include:
     - **Program**: Applies the rule to a specific program.
     - **Port**: Applies the rule to a specific port (e.g., TCP or UDP).
     - **Predefined**: Applies a rule to predefined services.
     - **Custom**: Allows you to specify detailed conditions.
   - Choose the appropriate rule type based on your needs.
   - ![Step 5](https://github.com/user-attachments/assets/6af81343-8acf-4994-a219-de4ed640273e)

5. **Specify Programs**:
   - If applicable, select whether the rule applies to a **specific program** or **all programs** on the system.
   - ![Step 6](https://github.com/user-attachments/assets/dac4a900-04d2-4afe-b48b-8f3a7cba405a)

6. **Define Action**:
   - Choose the action to be taken when the connection matches the conditions you’ve set:
     - **Allow the connection**.
     - **Block the connection**.
     - **Allow the connection only if it is secured** (requires that the connection is authenticated and encrypted).
     - ![Step 7](https://github.com/user-attachments/assets/e1b6294d-af5b-4166-a6f0-3c0e4b988763)

7. **Set Rule Application Conditions**:
   - Specify when the rule should be applied:
     - **Domain**: Applies when the computer is connected to a domain.
     - **Private**: Applies when connected to a private network (e.g., home or work network).
     - **Public**: Applies when connected to a public network (e.g., coffee shop Wi-Fi).
     - ![Step 8](https://github.com/user-attachments/assets/3b433edb-d896-4716-b3e3-a9a783271834)

8. **Name and Finalize the Rule**:
   - Give the rule a meaningful name (e.g., "Block Port 445") to identify it easily in the future.
   - Review the settings, and click **Finish** to apply the rule.
   - ![Step 9](https://github.com/user-attachments/assets/3a440e29-3ff7-49c2-8cf5-2f57facf9b8b)
