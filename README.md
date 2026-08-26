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
- The Security Operations environment architecture was designed using draw.io and deployed locally using VMware Workstation to support the complete security monitoring workflow:
               ```Telemetry Generation → Collection → SIEM → Detection → Investigation → Ticketing → Response```
- The environment included:
  - Elastic and Kibana for centralized security monitoring
  - Fleet Server for centralized endpoint management
  - Windows and Ubuntu endpoints for telemetry generation
  - osTicket for incident and case management
  - Mythic C2 for controlled adversary simulation
  - Kali Linux for attack simulation
  - A dedicated SOC Analyst workstation for monitoring and investigation.
- All components were deployed within a dedicated private network using the 192.168.126.0/24 address range.

📌 [Insert: Logical Architecture Diagram]

2. Elastic Stack Platform Evaluation

Reviewed the architecture and responsibilities of the Elastic Stack to understand how its components work together as a SIEM platform.

Elasticsearch

Evaluated Elasticsearch as the centralized search and analytics datastore responsible for storing and querying security telemetry such as:

Windows Event Logs
Sysmon events
Linux authentication logs
Security telemetry

Elasticsearch also provides:

ES|QL querying
REST APIs
JSON-based data interaction
Search and analysis capabilities
Logstash

Reviewed Logstash as a telemetry processing pipeline capable of:

Collecting data from multiple sources
Filtering events
Parsing fields
Transforming telemetry
Forwarding processed data to Elasticsearch
Kibana

Evaluated Kibana as the primary analyst interface for:

Log investigation
Data exploration through Discover
ES|QL queries
Lens visualizations
Dashboards
Alerting
Reporting
Telemetry Collection

Reviewed the two primary Elastic telemetry collection approaches.

Beats

Filebeat — log collection
Metricbeat — system metrics
Packetbeat — network telemetry
Winlogbeat — Windows Event Logs
Auditbeat — audit data
Heartbeat — uptime monitoring

Elastic Agent

Centralized endpoint telemetry and management through Fleet
Elastic vs. Traditional SIEM Architecture
Elastic Stack	Equivalent SIEM Function
Elasticsearch	Indexer / Search & Analytics
Logstash	Heavy Forwarder / Processing Pipeline
Kibana	Web / Analyst Interface
Beats / Elastic Agent	Data Collection / Forwarders

The evaluation highlighted several benefits of the Elastic platform:

Centralized logging
Flexible telemetry ingestion
Search and investigation capabilities
Security visualizations
Scalability
Broad integration ecosystem

3. Elasticsearch Deployment & Configuration

Provisioned a dedicated Ubuntu Server 22.04 virtual machine to host Elasticsearch.

Configuration Performed
Installed Elasticsearch
Secured the generated security auto-configuration credentials
Modified elasticsearch.yml
Configured network.host
Enabled HTTP port 9200
Enabled Elasticsearch to start automatically
Started the Elasticsearch service
Verified service status using systemctl
Service Management
systemctl daemon-reload
systemctl enable elasticsearch.service
systemctl start elasticsearch.service
systemctl status elasticsearch.service

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
