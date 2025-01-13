# Installation Guide

## Prerequisites
- Ubuntu 18.04+ on all nodes
- Sufficient memory and storage for Elasticsearch

### Step 1: Update System
```bash
-sudo apt update
-sudo apt install apt-transport-https

```

### Step 2: Install OpenJDK
Install OpenJDK 8, which is required by Elasticsearch:


```bash
sudo apt install openjdk-8-jdk
java -version
```

### Step 3: Install Elasticsearch

```bash
sudo apt-get install gnupg
wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo apt-key add -
sudo sh -c 'echo "deb https://artifacts.elastic.co/packages/7.x/apt stable main" > /etc/apt/sources.list.d/elastic-7.x.list'
sudo apt update
sudo apt install elasticsearch
sudo systemctl enable elasticsearch.service
sudo systemctl start elasticsearch.service
```

