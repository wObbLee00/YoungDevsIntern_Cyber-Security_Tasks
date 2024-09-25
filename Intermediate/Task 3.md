### Task 3: Analyzing Network Traffic with Wireshark

In this task, I used **Wireshark** to capture and analyze network traffic, specifically focusing on TCP and UDP packets. Here are the steps I followed:

1. **Launch Wireshark:**
   - Opened the Wireshark application, which displayed available network interfaces such as Wi-Fi and local area connections.
   - ![Step 1](https://github.com/user-attachments/assets/b45a1ca3-c99d-4e74-964b-3977da28ec46)

   
2. **Select Network Interface:**
   - Chose the **Wi-Fi** interface to start monitoring the wireless network traffic.
   - ![Step 2](https://github.com/user-attachments/assets/96958839-51e0-4855-8da1-582fc9a82e22)


3. **Capture Packets:**
   - Initiated the packet capture, allowing Wireshark to record all network traffic over the selected interface. I collected a total of **190 packets** for analysis.
   - ![Step 3](https://github.com/user-attachments/assets/e55392f8-48b9-42c4-9bf9-28b65ae0fcc9)


4. **Apply Display Filters:**
   - From the **Analyze** option in the top menu, I accessed the **Display Filter** section, which showed various predefined filters.
   - In the top search bar labeled "Apply a display filter," I typed **tcp** to filter and display all TCP-related packets.
   - Similarly, I applied the **udp** filter, which displayed only UDP packets.
   - ![Step 4](https://github.com/user-attachments/assets/cba9d32b-7a0c-462f-a73b-57b724044e6b)
   - ![Step 5](https://github.com/user-attachments/assets/b8de7fe4-40fe-466d-a748-00848eabef75)


5. **View I/O Graphs:**
   - Clicked on **Statistics** in the top menu and selected **I/O Graphs** to view a graphical representation of network traffic. The graph displayed TCP traffic errors, allowing for further analysis.
   - ![Step 5](https://github.com/user-attachments/assets/6c5b727e-fea3-4e91-8222-b65336679862)

6. **Analysis of Packets:**
  
    1. **Initial Handshake (TCP, TLS, QUIC)**:
   - Packets 1-3 show the **TCP three-way handshake** between the local machine and an external server, indicating the start of a communication session. 

    2. **Encrypted Traffic**:
   - Many packets (such as 10, 12, 14) involve **encrypted TLS data**. 

    3. **QUIC Protocol**:
   - Packets like 50-90 involve QUIC, a relatively new protocol running over UDP for faster and more secure web communications (used by platforms like Google).

    4. **Connection Resets and Alerts**:
   - Packets like 21 and 22 show **RST, ACK flags**, indicating connection resets. Reset flags can suggest issues with connections or intentional termination.

    5. **DNS Queries**:
   - Packet 43 and 44 show **DNS queries** from your local machine to the router, specifically querying the domain `google.com`.

