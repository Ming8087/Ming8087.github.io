+++
date = '2026-01-29T23:27:06+08:00'
draft = false
title = '云原生入门：3步搭建本地Kubernetes测试环境'
tags = ["Kubernetes", "云原生", "本地开发"]
+++

对于刚接触云原生的开发者来说，搭建一个稳定的本地K8s环境是入门的第一步。本文基于 **Docker + Kind** 实现快速部署，无需复杂的硬件配置，适合新手学习和测试。

### 一、环境准备
- 前置条件：安装 Docker（版本 20.10+）
- 安装 Kind：`curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.20.0/kind-linux-amd64 && chmod +x ./kind && sudo mv ./kind /usr/local/bin/`

### 二、3步搭建K8s集群
1. **创建集群配置文件**
   创建 `kind-config.yaml`：
```yaml
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
- role: control-plane
  extraPortMappings:
  - containerPort: 80
    hostPort: 80
    protocol: TCP
```