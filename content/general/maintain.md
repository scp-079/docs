---
weight: 30
title: 日常维护
summary: 介绍如何对服务进行日常维护
type: docs
---

# 日常维护

本节介绍如何使用便捷命令，对服务进行更新、维护等操作。

---

## 针对特定程序的操作

> 本部分以 `SCP-079-PM` 的程序为例。

### 配置程序

```bash
config pm
```

### 查看程序日志

```bash
log pm
```

### 强制重启程序

```bash
restart pm
```

### 查看程序服务状态

```bash
status pm
```

### 重启程序

```bash
start pm
```

### 停止程序

```bash
stop pm
```

### 尝试在终端中运行程序

```bash
try pm
```

### 更新程序

```bash
update pm
```

---

## 全局操作

> 本部分是对服务器上运行的所有程序执行的操作

### 查看所有程序的服务状态

```bash
check
```

### 清空所有程序的日志文件

```bash
clear
```

### 禁用所有程序

```bash
disable
```

### 启用所有程序，并指定每日定时重启的时间

```bash
enable 00:13:00
```

### 修改自动填充的全局配置

```bash
global
```

> 注意，修改此配置只能影响下次搭建新机器人所自动填充的数值，已搭建的机器人不受此设置影响。

### 重启所有程序

```bash
refresh
```

### 显示所有程序的日志

```bash
show
```

### 停止所有程序的运行

```bash
shut
```

### 更新所有程序

```bash
upgrade
```
