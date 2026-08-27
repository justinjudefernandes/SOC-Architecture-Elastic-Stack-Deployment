# SOC Architecture & Elastic Stack Deployment

## 🎯 Objective:
Establish the Elastic Stack as the centralized SIEM foundation for a multi-system Security Operations environment. The objective was to define the environment architecture, deploy and evaluate Elasticsearch and Kibana, and configure the platform with the security, authentication, networking, and operational settings required for effective SOC monitoring.

## 📊 Project Overview:
Built a multi-system Security Operations environment using VMware Workstation to support security monitoring, endpoint monitoring, incident management, and controlled security testing. The environment used the Elastic Stack as the central security monitoring platform, with Elasticsearch used to collect, store, and search security information, and Kibana providing the main interface for monitoring, investigation, and dashboards. The project included installing and configuring Elasticsearch and Kibana, setting up network connectivity, managing user access and security credentials, and applying secure platform settings.

## 🏗️ Environment Architecture:

<img width="550" height="450" alt="image" src="https://github.com/user-attachments/assets/9db6d560-66db-42bb-bb06-9cf045d51661" /> <br>

The environment consisted of six infrastructure and endpoint systems and two workstations:
- Elastic & Kibana Server — centralized SIEM and log analytics platform
- Fleet Server — centralized Elastic Agent management
- osTicket Server — incident ticketing and case management
- Windows Server — RDP-enabled monitored endpoint
- Ubuntu Server — SSH-enabled monitored endpoint
- Mythic C2 Server — adversary simulation and C2 infrastructure
- SOC Analyst Workstation — analyst access to security platforms
- Kali Linux Workstation — attack simulation and telemetry generation

## 🧰 Tools & Technologies:
- VMware Workstation Pro
- draw.io / diagrams.net
- Ubuntu Server 22.04 LTS
- Elasticsearch
- Kibana
- Fleet Server
- Elastic Agent
- Windows Server
- osTicket
- Mythic C2 Framework
- Kali Linux

## 🛠️ Capabilities Demonstrated:
- Security Operations architecture and network design
- SIEM platform evaluation and architecture mapping
- Linux server provisioning and administration
- Elasticsearch deployment and service administration
- Kibana deployment and Elasticsearch enrollment
- Elastic Stack component and telemetry architecture
- Network service configuration
- Authentication and credential management
- Kibana encryption-key and keystore configuration
- Technical documentation and infrastructure visualization

## 📁 Key Deliverables:
- Logical Security Operations architecture diagram
- VMware-based Security Operations environment
- Segmented private network
- Operational Elasticsearch instance
- Operational Kibana instance enrolled with Elasticsearch
- Configured Elasticsearch and Kibana network services
- Verified Kibana administrative access
- Persistent Kibana encryption keys configured through the keystore
- Documented Elastic Stack architecture and SIEM component mapping

## 🔍 Implementation:
### 1. Environment Architecture & Design
- Designed the Security Operations environment architecture using **draw.io** and deployed the infrastructure locally using **VMware Workstation**.
- The environment was structured to support the complete security monitoring workflow:

<p align="center">
  <strong>Telemetry Generation → Collection → SIEM → Detection → Investigation → Ticketing → Response</strong>
</p>

- The environment included:
  - **Elastic and Kibana** — Centralized security monitoring and analysis
  - **Fleet Server** — Centralized endpoint management
  - **Windows and Ubuntu endpoints** — Security and system telemetry generation
  - **osTicket** — Incident and case management
  - **Mythic C2** — Controlled adversary simulation
  - **Kali Linux** — Attack and security testing
  - **SOC Analyst workstation** — Security monitoring and investigation
- All components were deployed within a dedicated private network using the **192.168.126.0/24** address range.

### 2. Elastic Stack Platform Evaluation
Reviewed the main components of the **Elastic Stack** to understand how they work together to provide a centralized security monitoring and analysis platform.

#### a. Elasticsearch
- Evaluated **Elasticsearch** as the central system for storing, searching, and analyzing security data.
- Security data can include:
  - Windows Event Logs
  - Sysmon events
  - Linux authentication logs
  - Other security-related activity
- Reviewed its search, analysis, and API capabilities for investigating security events.

#### b. Logstash
- Reviewed **Logstash** as the data processing component.
- It can collect information from different sources, clean and organize the data, and send it to Elasticsearch for analysis.

#### c. Kibana
- Evaluated **Kibana** as the main interface used by security analysts.
- It supports:
  - Investigating security events
  - Searching and exploring data
  - Creating visualizations and dashboards
  - Running queries
  - Monitoring alerts
  - Generating reports

#### d. Telemetry Collection
- Reviewed the main methods used to collect security and system information.

##### i. Beats
- **Filebeat** — Collects log files
- **Metricbeat** — Collects system performance information
- **Packetbeat** — Collects network activity
- **Winlogbeat** — Collects Windows Event Logs
- **Auditbeat** — Collects security and audit information
- **Heartbeat** — Monitors system and service availability

##### ii. Elastic Agent
- Reviewed **Elastic Agent** as a centralized solution for collecting endpoint security and system information.
- Fleet can be used to centrally manage Elastic Agents across multiple endpoints.

### Elastic vs. Traditional SIEM Architecture

| Elastic Stack | Equivalent SIEM Function |
|---|---|
| Elasticsearch | Data Storage, Search & Analytics |
| Logstash | Data Processing & Collection |
| Kibana | Analyst / Security Operations Interface |
| Beats / Elastic Agent | Data Collection / Forwarders |

The evaluation demonstrated that the **Elastic Stack can provide a centralized platform for collecting, storing, searching, visualizing, and investigating security data**, while also supporting scalability and integration with a wide range of security technologies.

### 3. Elasticsearch Deployment & Configuration
- Set up a dedicated Ubuntu Server to host Elasticsearch, the core component responsible for storing and processing security data.
- Installed and configured Elasticsearch for secure operation.
- Configured the server's network settings and enabled communication through the required port.
- Secured the automatically generated security credentials.
- Configured Elasticsearch to start automatically when the server is restarted.
- Started the Elasticsearch service and verified that it was running successfully.
- Performed basic service management and operational checks to ensure the platform was ready for use.

📌 Refer to the below screenshots: (left to right)

<img width="390" height="230" alt="image" src="https://github.com/user-attachments/assets/4c3e59e4-15c3-4f3a-9df4-eb2172944986" />
<img width="390" height="230" alt="image" src="https://github.com/user-attachments/assets/763f79d4-1b7d-459c-ba40-d75ce97bdf97" />
<img width="390" height="230" alt="image" src="https://github.com/user-attachments/assets/824273bf-8764-46e2-9f13-c9b06ef3389a" />
<img width="390" height="230" alt="image" src="https://github.com/user-attachments/assets/4447eeaf-0684-4226-a83f-e7c70388c70e" />
<img width="390" height="230" alt="image" src="https://github.com/user-attachments/assets/a6139671-41ae-4eca-879f-43f2a191ff29" />
<img width="390" height="230" alt="image" src="https://github.com/user-attachments/assets/f6f1ed5a-be05-4d6e-8948-4fba4d4a21d3" />
<img width="390" height="230" alt="image" src="https://github.com/user-attachments/assets/8c61cd07-1c0b-4298-9e83-5313daf6c124" />
<img width="390" height="230" alt="image" src="https://github.com/user-attachments/assets/27e73605-a63f-4bfc-9b71-0dc1590e8a96" />

### 4. Kibana Deployment & Elasticsearch Enrollment:
Installed **Kibana** on the Elastic server and connected it to **Elasticsearch** to provide a user-friendly interface for security monitoring and investigation.

#### Configuration Performed:

- Installed and configured **Kibana**
- Configured the server network settings and **HTTP port 5601**
- Enabled Kibana to start automatically with the server
- Started and verified that the Kibana service was running successfully
- Connected Kibana to **Elasticsearch** using a secure enrollment process
- Verified that Kibana was communicating correctly with Elasticsearch
- Confirmed administrative access using the **elastic** account

#### Service Management:
```
systemctl daemon-reload
systemctl enable kibana.service
systemctl start kibana.service
systemctl status kibana.service
```

📌 Refer to the below screenshots: (left to right)

<img width="390" height="230" alt="image" src="https://github.com/user-attachments/assets/e74b12d5-dbee-4cd5-a04d-450ac495fb77" />
<img width="390" height="230" alt="image" src="https://github.com/user-attachments/assets/74552d27-5446-4a04-aebe-d3cf764fa5c4" />
<img width="390" height="230" alt="image" src="https://github.com/user-attachments/assets/665a363b-7b23-4d75-8adc-392248497a67" />
<img width="390" height="230" alt="image" src="https://github.com/user-attachments/assets/6a403c3b-3e38-4e14-ab73-03ef19a0efd9" />
<img width="785" height="230" alt="image" src="https://github.com/user-attachments/assets/1675b48d-9f96-44f8-baee-9ae025e48d80" />

### 5. Kibana Security & Encryption Configuration:
Configured **Kibana's security settings** to protect sensitive information and ensure that encryption keys remain available after system restarts.

#### Configuration Performed:
- Created secure, persistent encryption keys for Kibana
- Stored the keys securely in the **Kibana keystore**
- Enabled encryption for Kibana's protected information
- Restarted Kibana to apply the security configuration
- Verified that the encryption settings remained active after the restart

This ensured that Kibana's encryption keys were **securely stored and retained across service restarts**, providing consistent protection for sensitive data.

📌 Refer to the below screenshots: (left to right)

<img width="390" height="230" alt="image" src="https://github.com/user-attachments/assets/3c15ad27-14eb-437a-b340-fa12cff08813" />
<img width="390" height="230" alt="image" src="https://github.com/user-attachments/assets/13646545-d79d-4337-8a38-8b5305070183" />
<img width="390" height="230" alt="image" src="https://github.com/user-attachments/assets/6fa5d2fb-046a-4196-98c4-41f0acb8bc6f" />
<img width="390" height="230" alt="image" src="https://github.com/user-attachments/assets/a571ba15-3830-4f7e-a49a-b298d8716c9b" />
<img width="390" height="230" alt="image" src="https://github.com/user-attachments/assets/64a3baf1-9cda-4b68-989a-a096cac886e0" />
<img width="390" height="230" alt="image" src="https://github.com/user-attachments/assets/67e76d84-5d39-42fe-a089-9446de5a76a5" />
<img width="390" height="230" alt="image" src="https://github.com/user-attachments/assets/c968c5be-8e1a-4ff6-988e-29491916149f" />
<img width="390" height="230" alt="image" src="https://github.com/user-attachments/assets/4ca58748-0886-4825-b646-a32a0740ac93" />
<img width="390" height="230" alt="image" src="https://github.com/user-attachments/assets/74add54f-2f2f-490f-af17-3da008563349" />
<img width="390" height="230" alt="image" src="https://github.com/user-attachments/assets/8e4ad444-7713-4521-b15e-94b19c711fd5" />
<img width="390" height="230" alt="image" src="https://github.com/user-attachments/assets/321d6f74-261b-4033-ab51-07573c5bb537" />
<img width="390" height="230" alt="image" src="https://github.com/user-attachments/assets/5313858e-4579-442d-80fb-2a86ea38ad71" />
<img width="390" height="230" alt="image" src="https://github.com/user-attachments/assets/3db76325-9f1f-49ee-9b12-835af4e0d0ed" />
<img width="390" height="230" alt="image" src="https://github.com/user-attachments/assets/3951151c-3e4f-415e-bb0d-3395a66106aa" />
<img width="785" height="230" alt="image" src="https://github.com/user-attachments/assets/914ceb6a-b7e0-4b7f-88a2-39fbbe64eaa0" />
