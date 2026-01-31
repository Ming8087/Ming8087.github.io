+++
date = '2026-01-29T23:27:06+08:00'
draft = false
title = 'Cloud Native Getting Started: Build a Local Kubernetes Testing Environment in 3 Steps'
tags = ["Kubernetes", "Cloud Native", "Local Development"]
+++

For developers new to cloud-native technologies, setting up a stable local K8s environment is the first step to getting started. This article implements rapid deployment based on **Docker + Kind**, requiring no complex hardware configurations, and is suitable for beginners to learn and test.

### I. Environment Preparation
- Prerequisite: Docker installed (version 20.10+)
- Install Kind: `curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.20.0/kind-linux-amd64 && chmod +x ./kind && sudo mv ./kind /usr/local/bin/`

### II. Build K8s Cluster in 3 Steps
1. **Create Cluster Configuration File**
   Create `kind-config.yaml`:
```yaml
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
- role: control-plane
  extraPortMappings:
  - containerPort: 80
    hostPort: 80
    protocol: TCP