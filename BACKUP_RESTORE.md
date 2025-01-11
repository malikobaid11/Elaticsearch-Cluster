
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
    "bucket": "test-abc",
    "base_path": "malikobaid/testrepo",
    "region": "eu-west-1",
    "access_key": "<AWS_ACCESS_KEY>",
    "secret_key": "<AWS_SECRET_KEY>"
  }
}'


# Backup Data
curl -X PUT "http://<Master Node IP>:8917/_snapshot/s3_repository/snapshot_1?wait_for_completion=true"

# Restore Data 
curl -X POST "http://<Master Node IP>:8917/_snapshot/s3_repository/snapshot_1/_restore?wait_for_completion=true"
