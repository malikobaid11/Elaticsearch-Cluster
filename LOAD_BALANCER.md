


# Load Balancer Configuration

## Nginx Configuration
Edit `/etc/nginx/sites-available/default`:

### Load Balancing
```plaintext
upstream backend {
    server 172.16.100.161:8917;
    server 172.16.100.164:8917;
}

server {
    listen 80;
    location / {
        proxy_pass http://backend;
    }
}
```

### Reverse Proxy
```plaintext
server {
    listen 8080;
    location / {
        proxy_pass http://172.16.100.161:5601;
    }
}
```

Restart Nginx:

```bash
sudo systemctl restart nginx
```

