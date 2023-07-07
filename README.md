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

Service to be used in Lens:
```
prometheus/prometheus-server:9090
```

---

Add grafana repo:
```bash
helm repo add grafana https://grafana.github.io/helm-charts
helm repo update
```

Install grafana:
```bash
helm upgrade -i grafana grafana/grafana \
  --create-namespace \
  --namespace grafana \
  --set service.type=LoadBalancer
```

Get password for dashboard:
```
kubectl get secret --namespace grafana grafana \
  -o jsonpath="{.data.admin-password}" \
  | base64 --decode ; echo
```

---

Install kube-state-metrics:
```bash
helm install kube-state-metrics prometheus-community/kube-state-metrics \
  --create-namespace \
  --namespace prometheus
```


