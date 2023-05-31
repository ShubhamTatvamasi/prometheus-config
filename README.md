# prometheus-config

### helm

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

Install kube-state-metrics:
```bash
helm install kube-state-metrics prometheus-community/kube-state-metrics \
  --create-namespace \
  --namespace prometheus
```

Service to be used in Lens:
```
prometheus/prometheus-server:9090
```
