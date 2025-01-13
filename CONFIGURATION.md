
---

#### **CONFIGURATION.md**
```markdown
# Configuration Guide

## Elasticsearch Cluster
```

### Master Nodes Configuration
Edit `/etc/elasticsearch/elasticsearch.yml`:
```yaml
cluster.name: goto-cluster
node.name: es-master
node.data: false
node.master: true
node.ingest: true
network.host: <Master Node IP>
discovery.seed_hosts: ["<Master Node IP>"]
cluster.initial_master_nodes: ["<Master Node IP>"]
```

### Data Nodes Configuration
Edit `/etc/elasticsearch/elasticsearch.yml`:
```yaml
cluster.name: goto-cluster
node.name: es-data
node.data: true
node.master: false
node.ingest: true
network.host: <Data Node IP>
discovery.seed_hosts: ["<Master Node IP>"]
```


