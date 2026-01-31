+++
date = '2026-01-10T09:00:00+08:00'
draft = false
title = 'Prometheus + Grafana 实战：10分钟搭建K8s监控面板'
tags = ["Prometheus", "Grafana", "K8s监控", "DevOps"]
+++

监控是云原生系统的“眼睛”，**Prometheus + Grafana** 是目前最流行的监控组合。本文教你快速在 K8s 集群中部署这套工具，并配置可视化面板。

### 一、环境准备
- 已搭建的 K8s 集群（参考我的第一篇博客）
- 安装 Helm（K8s 包管理工具）

### 二、快速部署 Prometheus
1. 添加 Helm 仓库
```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update
```