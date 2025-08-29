# Mini SIEM on Kali Linux

This project implements a Mini Security Information and Event Management (SIEM) system on Kali Linux using Zeek for network monitoring, Elasticsearch for storage, Kibana for visualization, and Logstash for log ingestion.

## Features
- Ingested 1773 Zeek log documents into Elasticsearch (index: zeek-2025089).
- Set up a basic index pattern in Kibana.
- Attempted a detection rule for .onion domains.
- Runs on http://localhost:5601.

## Setup
- Install dependencies: Elasticsearch, Kibana, Logstash, Zeek.
- Configure elasticsearch.yml, kibana.yml, and Logstash pipeline (files included).
- Start services: `systemctl start elasticsearch`, `systemctl start kibana`, etc.
- Capture traffic with Zeek and ingest logs from /home/kali/Desktop/zeek_logs/.

## Challenges
- Encountered permission issues with kibana.yml.
- Resolved an invalid_index_template_exception (template not found).
- Had some minor issues regarding file access.

## Future Improvements
- Fix remaining permission errors.
- Add dashboards for visualization.
- Document full troubleshooting steps.

## Usage
- Access Kibana at http://localhost:5601.
- Check indices with `curl -X GET http://localhost:9200/_cat/indices/zeek*?v`.
