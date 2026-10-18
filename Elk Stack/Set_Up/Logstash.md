# Logstash Documentation

## 1. Overview
Logstash is  data-processing component of the `ELK` Stack. It collects, processes, and forwards log data to Elasticsearch for indexing and analysis in Kibana.

## 2. Configuration Files
- Main configuration: `/etc/logstash/logstash.yml`
- Pipeline configuration: `/etc/logstash/conf.d/logstash.conf`
- Pipeline settings: `/etc/logstash/pipelines.yml`

## 3. Pipeline Workflow
1. **Input:** Receives log data from the configured source.
2. **Filter:** Parses, transforms events when filters are configured.
3. **Output:** Sends processed events to the configured destination, such as Elasticsearch.

## 4. Service Management

To check service status:

```bash
sudo systemctl status logstash --no-pager
```

Restart Logstash:

```bash
sudo systemctl restart logstash
```

Stop Logstash:

```bash
sudo systemctl stop logstash
```

## 6. Exported Configuration and Logs

Expected files:
- `logstash-pipeline-documentation.txt`
- `logstash-status.txt`
- `logstash-service-logs.txt`

## 7. Integration with Elasticsearch and Kibana

Logstash forwards events to Elasticsearch according to the configured pipeline output. Kibana can then search, filter, visualize, and monitor the indexed events.


## 8. Security Considerations
- Never publish credentials, passwords, or API keys.
- Review logs for sensitive information before sharing.
- Restrict access to configuration and exported files.
- Use authorized log sources for security monitoring.

## 10. Project Outcome
Logstash provides the ingestion and processing layer of the Mini-SIEM, connecting the selected log source to Elasticsearch for subsequent analysis and visualization in Kibana.
