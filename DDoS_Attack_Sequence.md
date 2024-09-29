# Lab 6: Mermaid Diagrams
## DDoS Attack Sequence
 This will be a diagram to show how DDoS Attack is done. In the section below it will also give a short reveiew of the concept of a DDoS Attack.

 ### DDoS Attack Concepts
  * **Attacker**: Launches the attack by controlling a network of compromised devices, or BotNet.
  * **BotNet (Bots)**: Compromised systems that send large volumes of requests to overwhelm the web server.
  * **Web Server**: The target of the attack, which becomes overwhelmed by the traffic.
  * **Firewall/Defence Systems**: Detect and mitigate the attack by blocking malicious traffic.

  # DDoS Attack Sequence Diagram

```mermaid
sequenceDiagram
    participant Attacker
    participant BotNet
    participant WebServer
    participant Firewall

    Attacker->>BotNet: Instruct bots to send traffic
    BotNet->>WebServer: Overwhelm server with requests
    WebServer->>Firewall: Server detects abnormal traffic
    Firewall-->>WebServer: Initiates traffic analysis
    Firewall-->>BotNet: Blocks suspicious IP addresses
    BotNet-->>Attacker: Reports blocked connections
    Firewall->>WebServer: Mitigates the attack
  
  ## Explanation of the Sequence Diagram

1. **Attacker Instructs BotNet**: The attacker controls a network of compromised systems (BotNet) and instructs them to start sending large volumes of traffic to the target web server.
   
2. **BotNet Sends Requests to WebServer**: The compromised bots flood the web server with excessive requests, overloading it and leading to service disruptions.

3. **WebServer Detects Abnormal Traffic**: The web server starts struggling to handle the high volume of requests. It detects unusual traffic patterns and triggers a request to the firewall for further analysis.

4. **Firewall Analyzes Traffic**: The firewall or other defense mechanisms analyze the incoming traffic, identifying that much of it is coming from suspicious sources.

5. **Firewall Blocks Suspicious IPs**: After analyzing the traffic, the firewall blocks the IP addresses of the bots to reduce the load on the web server.

6. **BotNet Reports Back to Attacker**: The BotNet systems report back to the attacker, informing them that some of the connections are being blocked by the firewall.

7. **Firewall Mitigates the Attack**: With the IPs blocked, the firewall reduces the impact of the DDoS attack on the web server, allowing legitimate traffic to pass through while continuing to monitor for further attacks.
