# Kibana Documentation

## 1. Overview

Kibana is the visualization and analysis interface for the project. It connects to Elasticsearch to display web log records, facilitating interactive searches, and present aggregated security information through dashboards.

## 2. Environment

- Operating system: Kali Linux
- Kibana URL: `http://127.0.0.1:5601`
- Data source: `kibana_sample_data_logs`
- Main applications used: Discover and Dashboard

## 3. Accessing Kibana

To restart Kibana

```bash
sudo systemctl restart kibana
```

Open the following address in a browser on the Kali machine:

http://127.0.0.1:5601

## 4. Discover

Discover was used to inspect individual web log records.

The investigation included:

- Reviewing `timestamps`.
- Examining `client IP addresses`.
- Inspecting `HTTP response codes`.
- Searching requested `URLs` and `request` details.
- Filtering records with `HTTP responses`.

## 5. Dashboard Configuration

A  dashboard titled `Mini SIEM – Web Log` was created using the sample web logs.

The dashboard contains six panels:

1. `Web Requests` : Displays the total number of records.
2. `Web Traffic Over Time` : Displays changes in event volume over time.
3. `Top Client IPs` : Client IP addresses by descending order.
4. `HTTP Response Distribution` : Summarizes HTTP response codes.
5. `Responses` : Displays a table of response related statistics such as timestamps,client Ip.
6. `Recent Web Events` : Presents a table of recent aggregated web log information.

## 6. Observed Results

At the time of the captured dashboard screenshot, the total web request metric displayed 1,619.

The response distribution showed:

- HTTP 200: 92.15% records
- HTTP 404: 5.13% records
- HTTP 503: 2.72% records

## 7. Saved Objects and Export

Kibana supports exporting saved objects, including dashboards, visualizations, searches, and data views.

To export the dashboard:

1. Open Kibana.
2. Navigate to Stack Management => Saved Objects page.
3. Select the dashboard and its related objects.
4. Choose Export.
5. Save the downloaded NDJSON file in the repository's directory.

## 8. Limitations

The dashboard uses sample web logs rather than a continuously collected production log stream. The displayed patterns are useful for learning and testing investigative queries but are not proof of real attacks.

## 9. Conclusion

Kibana provides the investigation and visualization layer of the Mini SIEM. The dashboard summarizes web activity and supports further analysis of errors, client traffic, and potentially suspicious request patterns.