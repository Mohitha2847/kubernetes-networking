# Kubernetes Networking

## Overview

This project demonstrates Kubernetes networking concepts including Pods and Services.

The objective of this project is to understand how Kubernetes Services expose applications within a cluster and how Pods communicate through internal networking.

---

## Features

- Creation of a Kubernetes Pod
- Creation of a Kubernetes Service
- Internal networking using ClusterIP
- Service discovery using Endpoints
- Familiarity with kubectl commands

---

## Project Structure

```
kubernetes-networking

│
├── pod.yaml
├── service.yaml
├── README.md

└── assets
    ├── pod-yaml.png
    ├── service_created.png
    ├── endpoints.png
    ├── api-resources.png
    └── get-all.png
```

---

## Pod Configuration

The `pod.yaml` file creates an Nginx Pod with the label:

```yaml
app: my-app
```

The Pod exposes port 5000 internally.

---

## Service Configuration

The `service.yaml` file creates a Kubernetes Service of type `ClusterIP`.

The service:

- Selects Pods with label `app: my-app`
- Routes traffic to the Pod
- Exposes the application inside the Kubernetes cluster

---

## kubectl Commands Used

### Check Kubernetes Installation

```bash
kubectl version --client

kubectl cluster-info
```

### Create Pod

```bash
kubectl apply -f pod.yaml
```

### Verify Pod

```bash
kubectl get pods

kubectl get pods -o wide
```

### Create Service

```bash
kubectl apply -f service.yaml
```

### Verify Service

```bash
kubectl get services

kubectl describe service my-service
```

### Verify Internal Networking

```bash
kubectl get endpoints my-service
```

### Explore Kubernetes Resources

```bash
kubectl api-resources

kubectl get all
```

---

## Verification

The Kubernetes control plane was successfully started using Docker Desktop.

The Pod was created and reached the Running state.

The Service was created successfully and assigned a ClusterIP.

The endpoint information confirms that the Service discovered the Pod and can route traffic internally within the cluster.

---

## Concepts Learned

- Kubernetes Pods
- Kubernetes Services
- ClusterIP Networking
- Service Discovery
- Endpoints
- kubectl Command Line Tool
- Internal Cluster Communication

---

## Outcome

Successfully created and verified Kubernetes networking components using Pods and Services, demonstrating internal communication and service discovery within a Kubernetes cluster.
