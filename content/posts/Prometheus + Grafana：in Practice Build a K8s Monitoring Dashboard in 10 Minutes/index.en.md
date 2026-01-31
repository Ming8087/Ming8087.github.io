+++
date = '2026-01-10T09:00:00+08:00'
draft = false
title = 'Prometheus + Grafana in Practice: Build a K8s Monitoring Dashboard in 10 Minutes'
tags = ["Prometheus", "Grafana", "K8s Monitoring", "DevOps"]
+++

Monitoring is the "eyes" of cloud-native systems, and **Prometheus + Grafana** is currently the most popular monitoring combination. This article will teach you how to quickly deploy this toolset in a K8s cluster and configure a visualization dashboard.

### I. Environment Preparation
- A pre-built K8s cluster (refer to my first blog post)
- Helm installed (K8s package management tool)

### II. Quickly Deploy Prometheus
1. Add Helm Repository
```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update