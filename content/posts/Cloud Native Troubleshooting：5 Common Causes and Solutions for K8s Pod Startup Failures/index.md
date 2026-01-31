+++
date = '2026-01-20T11:00:00+08:00'
draft = false
title = '云原生踩坑记：K8s Pod 启动失败的5个常见原因及解决方案'
tags = ["K8s", "问题排查", "云原生", "运维"]
+++

在 K8s 日常使用中，Pod 启动失败是最常见的问题。我整理了5个高频踩坑场景和对应的排查方法，帮你快速定位问题。

### 一、原因1：镜像拉取失败
**现象**：Pod 状态显示 `ImagePullBackOff`
**排查命令**：
```bash
kubectl describe pod <pod-name> | grep ImagePull
```