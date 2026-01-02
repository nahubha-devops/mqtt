# MQTT v3.0.7 on Kubernetes

## Quick Start

1. **Deploy to Kubernetes:**
   ```bash
   kubectl apply -f namespace.yaml
   kubectl apply -f rinomqtt-config.yaml
   kubectl apply -f rinomqtt-deployment.yaml
   ```

2. **Check deployment:**
   ```bash
   kubectl get pods -l app=rinomqtt -n mqtt
   kubectl get svc rinomqtt-service -n mqtt
   ```

3. **Get service endpoint:**
   ```bash
   kubectl get svc rinomqtt-service -n mqtt
   ```

## Connection Details

- **MQTT Port:** 1883
- **WebSocket Port:** 1884
- **HTTP Port:** 8080
- **Username:** protco_dev
- **Password:** password

## Test Connection

```bash
# Using mosquitto_pub/sub
mosquitto_pub -h <EXTERNAL_IP> -p 1883 -u protco_dev -P password -t "test/topic" -m "hello"
mosquitto_sub -h <EXTERNAL_IP> -p 1883 -u protco_dev -P password -t "test/topic"
```

## Features

- MQTT v3.0+ protocol support
- Authentication with username/password
- ACL permissions for topic access
- RocketMQ integration
- Shared subscriptions support