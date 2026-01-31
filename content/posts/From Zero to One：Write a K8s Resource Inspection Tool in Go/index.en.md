+++
date = '2026-01-15T14:00:00+08:00'
draft = false
title = 'From Zero to One: Write a K8s Resource Inspection Tool in Go'
tags = ["Go", "K8s", "Tool Development", "Cloud Native"]
+++

As a cloud-native developer, you often need to check the status of resources in a K8s cluster (such as abnormal Pods, unexposed Services, etc.). This article will teach you to write a lightweight inspection tool using Go language combined with the official K8s SDK.

### I. Technology Stack
- Programming Language: Go 1.21+
- Core Library: `k8s.io/client-go` (official K8s client library)

### II. Core Steps
1. **Initialize Go Project**
```bash
go mod init k8s-checker
go get k8s.io/client-go@v0.28.0