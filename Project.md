# Project Plan

## 1. Overview
**Project Title:** Mini-SIEM Using the ELK Stack

**Objective:** Build a lightweight Security Information and Event Management (SIEM) lab to collect, process, index, and visualize log data for basic security monitoring and analysis.

The project uses Elasticsearch, Logstash, and Kibana to demonstrate a log-monitoring workflow using locally available log data.

## 2. Objectives
1. Set up and configure Elasticsearch for storing and searching log events.
2. Configure Kibana to explore, filter, and visualize indexed log data.
3. Configure Logstash to ingest, parse, and forward log events.
4. Integrate custom log data into the ELK Stack.
5. Develop a centralized location for log analysis and troubleshooting.
6. Explore security-relevant events and identify potentially suspicious activity.
7. Document the architecture, configurations, testing procedures, and results.
8. Establish a reusable lab environment for future cybersecurity experiments.

## 3. Scope

### In Scope
- Local ELK Stack configuration and integration.
- Indexing and searching events in Elasticsearch.
- Data exploration and dashboard creation in Kibana.
- Basic monitoring and investigation of suspicious log patterns.
- Configuration backups, troubleshooting records, and project documentation.

### Out of Scope
- Enterprise-scale SIEM deployment.
- Automated blocking or remediation of attacks.
- Monitoring systems without authorization.
- High-availability clustering and large-scale distributed deployment.

## 4. Tools and Technologies

| Tool | Purpose |
|---|---|
| Kali Linux | Lab operating system |
| Elasticsearch | Log indexing, storage, and search |
| Logstash | Log ingestion and processing |
| Kibana | Log exploration and visualization |
| Bash | Administration and automation |

**Hardware consideration:** The lab is designed as native to Kali Linux.

## 5. Expected Outcomes
- A functional local ELK-based log-analysis lab.
- Centralized indexing and search of the selected log data.
- A validated Logstash ingestion pipeline.
- Kibana visualizations for exploring relevant events.
- Documented system architecture, configuration, testing, and limitations.
- A foundation for future SIEM and cybersecurity projects.

## 6. Success Criteria
- Elasticsearch responds successfully to health and search requests.
- Kibana connects to Elasticsearch and displays the relevant data.
- Logstash validates and runs the intended pipeline.