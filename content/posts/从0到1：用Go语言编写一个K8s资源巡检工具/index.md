+++
date = '2026-01-15T14:00:00+08:00'
draft = false
title = '从0到1：用Go语言编写一个K8s资源巡检工具'
tags = ["Go", "K8s", "工具开发", "云原生"]
+++

作为一名云原生开发者，经常需要检查 K8s 集群中的资源状态（比如 Pod 异常、Service 未暴露等）。本文教你用 Go 语言结合 K8s 官方 SDK 编写一个轻量级的巡检工具。

### 一、技术栈
- 编程语言：Go 1.21+
- 核心库：`k8s.io/client-go`（K8s 官方客户端库）

### 二、核心步骤
1. **初始化 Go 项目**
```bash
go mod init k8s-checker
go get k8s.io/client-go@v0.28.0
```