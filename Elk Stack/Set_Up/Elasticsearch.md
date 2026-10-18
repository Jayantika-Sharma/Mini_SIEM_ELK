# Elasticsearch Documentation 

## 1. Overview

`Elasticsearch` is a search & analytics engine used in the project. It stores and indexes the web log events so that they can be searched, filtered, aggregated, and analyzed.

The project uses Kibana's built-in sample web logs as the initial dataset.

## 2. Environment

- Operating system: Kali Linux
- Elasticsearch HTTP endpoint: `http://127.0.0.1:9200`
- Dataset index: `kibana_sample_data_logs`
- Data type: Ssh logs

## 3. Dataset Description

The sample dataset contains web activity records:

| Field | Description |
|---|---|
| `@timestamp` | Time associated with an event |
| `@version` |  The internal versioning schema format used by the Logstash indexer. |
| `_id_` | unique alphanumeric identifier |
| `_index_` | Elasticsearch index pattern |
| `bytes` | Response size in bytes |

## 4. Elasticsearch Verification

To check the Elasticsearch version and cluster information:

```curl -sS http://127.0.0.1:9200/```

To check cluster health:

```curl -sS 'http://127.0.0.1:9200/_cluster/health?pretty'```

List logs index:

```curl -sS 'http://127.0.0.1:9200/_cat/indices/logstash-*?v'```

Inspect the index mappings:

```curl -sS 'http://127.0.0.1:9200/logstash-*/_mapping?pretty'```

Retrieve sample documents:

```bash
curl -sS -X GET \
'http://127.0.0.1:9200/logstash-*/_search?pretty' \
-H 'Content-Type: application/json' \
-d '{"size": 5, "query": {"match_all": {}}}'
```

## 5. Data Storage and Search

Elasticsearch stores indexed documents in an index. Each document represents an individual log event and contains fields that support searching and aggregation.

Kibana uses Elasticsearch queries to retrieve records and calculate dashboard metrics.

## 6. Limitations

The dataset is intended for learning and demonstration. It represents live traffic from the Kali machine, but it cannot independently validate SSH brute-force activity or port scans.

## 7. Conclusion

Elasticsearch provides the searchable storage layer for the Mini SIEM. Its indexed web log records enable Kibana visualizations, filtering, and investigation workflows.