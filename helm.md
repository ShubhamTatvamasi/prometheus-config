# helm

Add prometheus helm repo:
```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
```

Install prometheus:
```bash
helm install prometheus prometheus-community/prometheus \
  --create-namespace \
  --namespace prometheus
```
