# SOC Architecture & Elastic Stack Deployment

## 🎯 Objective:
Establish the Elastic Stack as the centralized SIEM foundation for a multi-system Security Operations environment. The objective was to define the environment architecture, deploy and evaluate Elasticsearch and Kibana, and configure the platform with the security, authentication, networking, and operational settings required for effective SOC monitoring.

## 📊 Project Overview:
Designed and provisioned a multi-system Security Operations environment in VMware Workstation to support security monitoring, endpoint telemetry, centralized management, incident ticketing, and adversary simulation.

The environment was built around the Elastic Stack, with Elasticsearch providing centralized data storage and search capabilities and Kibana serving as the primary analyst interface for querying, visualization, and security operations.

The deployment included Elasticsearch and Kibana installation, network configuration, platform enrollment, administrative authentication, and persistent encryption-key configuration through the Kibana keystore.

## 🏗️ Environment Architecture

📌 Refer to the below screenshot:

<img width="873" height="700" alt="image" src="https://github.com/user-attachments/assets/9db6d560-66db-42bb-bb06-9cf045d51661" />

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
### 1. Environment Architecture & Design:
- The Security Operations environment architecture was designed using draw.io and deployed locally using VMware Workstation to support the complete security monitoring workflow: <br>
<p align="center">
  <strong>Telemetry Generation → Collection → SIEM → Detection → Investigation → Ticketing → Response</strong>
</p>

- The environment included:
  - Elastic and Kibana for centralized security monitoring
  - Fleet Server for centralized endpoint management
  - Windows and Ubuntu endpoints for telemetry generation
  - osTicket for incident and case management
  - Mythic C2 for controlled adversary simulation
  - Kali Linux for attack simulation
  - A dedicated SOC Analyst workstation for monitoring and investigation.
- All components were deployed within a dedicated private network using the 192.168.126.0/24 address range.

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

📌 [Insert: Elasticsearch Installation Screenshot]

📌 [Insert: Elasticsearch Service Status Screenshot]

4. Kibana Deployment & Elasticsearch Enrollment

Installed Kibana on the Elastic server and configured it to communicate with Elasticsearch.

Configuration Performed
Modified kibana.yml
Configured server.host
Configured HTTP port 5601
Enabled Kibana as a system service
Started and verified the Kibana service
Generated an Elasticsearch enrollment token
Enrolled Kibana with Elasticsearch
Completed Kibana verification
Authenticated using the elastic administrative account
Service Management
systemctl daemon-reload
systemctl enable kibana.service
systemctl start kibana.service
systemctl status kibana.service

📌 [Insert: Kibana Configuration Screenshot]

📌 [Insert: Kibana Enrollment Screenshot]

📌 [Insert: Kibana Dashboard Screenshot]

5. Kibana Security Configuration

Configured persistent Kibana encryption keys using the Kibana keystore.

Configuration Performed
Generated persistent Kibana encryption keys
Added the required keys to the Kibana keystore
Configured encryption for Kibana's protected data
Restarted Kibana to apply the configuration

This ensured that the required encryption keys persisted across Kibana service restarts rather than being regenerated.

📌 [Insert: Kibana Keystore Configuration Screenshot]

📌 Outcome

Successfully established the foundation of the Security Operations environment by:

Architecting the environment → Deploying Elasticsearch → Deploying Kibana → Enrolling the platform → Configuring security keys

This Elastic environment subsequently served as the centralized SIEM platform for the remainder of the 30-Day MyDFIR challenge, where Windows and Linux telemetry, Sysmon events, authentication activity, C2 telemetry, detection rules, dashboards, automated alerting, and EDR events were investigated and analyzed.
