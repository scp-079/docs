---
weight: 10
title: 服务器设置
summary: 介绍应对服务器所做的基础设置
type: docs
---

# 服务器设置

我们建议自建用户使用完整的 `Debian 10` 或 `Ubuntu 20.04` 系统来搭建服务。本节所描述的步骤均在此二者上测试通过，且本节提供的脚本仅支持基于 `Debian` 的系统。所有机器人都只能在 Python 3.6 及以上版本中运行。

{{< hint danger >}}
**注意**  

1. 如您不熟悉 Linux 下的操作，请勿使用其他系统。
2. 若您使用了 Docker，请确保容器内可通过终端使用 `systemd`，确保 `systemctl`、`loginctl` 命令可被正确执行。
<br /><br />
{{< /hint >}}

---

## 配置环境

请以 `root` 用户执行以下命令：

```bash
apt update && apt install curl -y
```

```bash
bash <(curl -s https://raw.githubusercontent.com/scp-079/scripts/master/root.sh)
```

{{< hint info >}}
**提示**  

1. 此脚本将提示您为创建的新用户 `scp` 指定一个密码，请设置较强壮的密码。
2. 执行此脚本后，系统的时区将被调整为 UTC，我们建议用户使用 UTC 时区，并且请在进行有关时间点的配置时，考虑到系统的时区、时间点的配置，对服务所面向的主要群体的影响。
<br /><br />
{{< /hint >}}

---

## 切换用户

脚本运行结束后，请切换至 `scp` 用户，以便进行「开始搭建」一节中所描述的操作。您可以使用 `su` 命令来切换至 `scp` 用户，也可以使用 `ssh` 工具登录到 `scp` 用户上。具体操作方法如下：

{{< tabs "uniqueid" >}}
{{< tab "su" >}}
### 使用 su 命令

仍在 `root` 用户下执行：

```bash
su - scp
```
{{< /tab >}}

{{< tab "ssh" >}}

### 使用 ssh 登录

退出 `root` 用户的登录会话后，重新登录至 `scp` 用户：

```bash
ssh scp@your_server
```
{{< /tab >}}
{{< /tabs >}}

---

至此，对服务器的配置已进行完毕。
