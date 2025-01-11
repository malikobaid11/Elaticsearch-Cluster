
---

#### **BACKUP_RESTORE.md**
```markdown
# Backup and Restore Guide

## Setup Backup Repository
```bash
curl -XPUT 'http://<Master Node IP>:8917/_snapshot/s3_repository?verify=false&pretty' \
-H 'Content-Type: application/json' -d'{
  "type": "s3",
  "settings": {
    "bucket": "test-epc",
    "base_path": "malikobaid/testrepo",
    "region": "eu-west-1",
    "access_key": "<AWS_ACCESS_KEY>",
    "secret_key": "<AWS_SECRET_KEY>"
  }
}'

