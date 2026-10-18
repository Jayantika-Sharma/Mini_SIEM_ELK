# Elasticsearch Documentation 

## 1. Overview

`Elasticsearch` is a search & analytics engine used in the project. It stores and indexes the web log events so that they can be searched, filtered, aggregated, and analyzed.

The project uses Kibana's built-in sample web logs as the initial dataset.

## 2. Environment

- Operating system: Kali Linux
- Elasticsearch HTTP endpoint: `http://127.0.0.1:9200`
- Sample dataset index: `kibana_sample_data_logs`
- Data type: Sample web server access logs

## 3. Dataset Description

The sample dataset contains web activity records:

| Field | Description |
|---|---|
| `@timestamp` | Time associated with an event |
| `clientip` | Client IP address |
| `response` | HTTP response status |
| `url` | Requested URL |
| `bytes` | Response size in bytes |
| `request` | HTTP request information |
| `agent` | Client user-agent information |
| `geo.src` | Source geographic information |

## 4. Elasticsearch Verification

To check the Elasticsearch version and cluster information:

```curl -sS http://127.0.0.1:9200/```

To check cluster health:

```curl -sS 'http://127.0.0.1:9200/_cluster/health?pretty'```

List logs index:

```curl -sS 'http://127.0.0.1:9200/_cat/indices/kibana_sample_data_logs?v'```

Inspect the index mappings:

```curl -sS 'http://127.0.0.1:9200/kibana_sample_data_logs/_mapping?pretty'```

Retrieve sample documents:

```bash
curl -sS -X GET \
'http://127.0.0.1:9200/kibana_sample_data_logs/_search?pretty' \
-H 'Content-Type: application/json' \
-d '{"size": 5, "query": {"match_all": {}}}'
```

## 5. Data Storage and Search

Elasticsearch stores indexed documents in an index. Each document represents an individual log event and contains fields that support searching and aggregation.

Kibana uses Elasticsearch queries to retrieve records and calculate dashboard metrics.

## 6. SIEM Use Cases

The stored data supports preliminary investigations into:

- HTTP error responses, including status codes 404 and 503.
- Client IP addresses generating large numbers of requests.
- Request patterns that may indicate web reconnaissance.
- Changes in request volume over time.
- Suspicious URL paths and repeated error events.


## 7. Limitations

The sample dataset is intended for learning and demonstration. It does not necessarily represent live traffic from the Kali machine, and it cannot independently validate SSH brute-force activity or port scans.

## 8. Conclusion

Elasticsearch provides the searchable storage layer for the Mini SIEM. Its indexed web log records enable Kibana visualizations, filtering, and investigation workflows.