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
