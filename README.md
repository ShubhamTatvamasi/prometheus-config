# prometheus-config


Add prometheus repo:
```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update
```

Install prometheus:
```bash
helm upgrade -i prometheus prometheus-community/prometheus \
  --create-namespace \
  --namespace prometheus
```
