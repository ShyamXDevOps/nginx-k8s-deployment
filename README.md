# NGINX Kubernetes Deployment

This repository contains a basic Kubernetes deployment controller manifest to run an **NGINX web server** with 3 replicas in a containerized environment.

It demonstrates a simple use of `Deployment` in Kubernetes for **load balancing**, **scalability**, and **stateless service management**.

---

## What This Does

- Deploys **NGINX** using a **Deployment controller**
- Runs **3 replica pods**
- Exposes **port 80** for HTTP traffic
- Useful for understanding the core structure of Kubernetes manifests

---

## Kubernetes Manifest Used

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deploy
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
        - name: nginx
          image: nginx
          ports:
            - containerPort: 80

