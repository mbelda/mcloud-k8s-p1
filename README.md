# Práctica 1 - Métricas y Visualización con Prometheus y Grafana en Kubernetes

### Comandos útiles

- Verificar el estado de los pods del stack de monitorización
```bash
kubectl get pods -n monitoring
```

- Mostrar todos los servicios Kubernetes desplegados en el namespace
```bash
kubectl get svc -n monitoring
```

- Redirigir el puerto 3000 de la máquina local al puerto 80 del servicio de Grafana, permitiendo acceder a la interfaz web en `http://localhost:3000`
```bash
kubectl port-forward -n monitoring svc/prometheus-grafana 3000:80
```

- Obtener la contraseña de Grafana
```bash
kubectl get secret -n monitoring prometheus-grafana -o jsonpath="{.data.admin-password}" | base64 --decode; echo
```
