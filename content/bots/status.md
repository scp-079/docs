---
title: STATUS
summary: 介绍如何在自建时配置 SCP-079-STATUS
type: docs
---

# STATUS

本文介绍搭建 `SCP-079-STATUS` 的注意事项，以及配置文件中各数值的意义。

请注意先参照[「通用步骤」](/general/)进行配置。

---

## 需要加入的频道

- SCP-079-CRITICAL
    - 必选
    - 应具有发送消息的权限

---

## 机器人性质

为 `常规 Bot`，需要在 [BotFather](https://t.me/BotFather) 处获取 `bot token`。

{{< hint info >}}
**提示**  
我们建议不同的服务器使用单独的机器人更新状态，避免同一机器人在同一频道中频繁编辑多个消息，防止因此受到 Telegram 对编辑消息的频率限制。
{{< /hint >}}

---

## 文件 `config.ini`

> 这是一个自定义的文件。文件应位于 `data/config/` 目录下，可参照 `examples/config.ini` 的格式进行设置。
>
> 需要对 `config.ini` 文件中内容为 `[DATA EXPUNGED]` 的全部键值进行修改。
>
> `api_id` 与 `api_hash` 可在[官网](https://my.telegram.org)获取。

```ini
[pyrogram]
api_id = [DATA EXPUNGED]
api_hash = [DATA EXPUNGED]
; 以上两条信息从官网申请获得

[plugins]
root = plugins
include =
    handlers.command

[proxy]
enabled = False
; 可根据需要自行决定是否使用 SOCKS5 代理
hostname = 127.0.0.1
port = 1080

[auth]
creator_id = [DATA EXPUNGED]
; 此处填写机器人所有者的用户 ID

[basic]
bot_token = [DATA EXPUNGED]
; 此处填写在 @BotFather 处获得的 token
prefix = /!
; 命令前的可用字符，如在群组中使用非常规命令前缀，需要机器人有获取普通消息的权限

[channels]
critical_channel_id = [DATA EXPUNGED]
; 此处填写紧急频道 SCP-079-CRITICAL 的 ID

[custom]
format_date = %Y/%m/%d %H:%M:%S
; 此处自定义显示日期时所使用的格式
format_time = %H:%M:%S
; 此处自定义显示时间时所使用的格式
interval = 3
; 此处填写正整数，表示更新状态的时间间隔，建议不小于 3，否则机器人可能频繁受到编辑消息的频率限制
manual_link = https://manuals.scp-079.org/bots/status/
; 此处填写使用手册的链接

[language]
lang = cmn-Hans
; 此处填写 languages 文件夹下所包含的 YAML 文件的对应名称
```

---

## 文件 `report.txt`

> 这是一个自定义的文件。文件应位于 `data/config/` 目录下，可参照 `examples/report.txt` 的格式进行设置。
>
> 此文件将作为机器人通过 `/send` 命令触发后，机器人在指定频道所发送的消息内容的模板。
>
> 当设定消息内容的样式时（链接、加粗、斜体、代码块），请内容遵从 HTML 格式，请见：<https://docs.pyrogram.org/topics/text-formatting#html-style>
>
> 此文件的内容可自由编写，但请注意保证状态替换后的文本不超过 4096 个字符。

> 以下是示例，仅供参考：

```
站点：<code>Site-01</code>

备注：<code>示例</code>
更新间隔：<code>$interval$</code>
时区：<code>UTC</code>

最后在线：<code>$last$</code>
操作系统：<code>$dist$</code>
内核：<code>$kernel$</code>
开机时长：<code>$up_time$</code>

平均负载：<code>$load$</code>
CPU 核心数量：<code>$cpu_count_logical$</code>
CPU 总占用：<code>$cpu_percent$</code>
CPU 各核心占用情况:
$cpu_percent_per$

内存总量: <code>$memory_total$</code>
空闲内存：<code>$memory_available$</code>
内存占用比：<code>$memory_percent$</code>
SWAP 总量：<code>$swap_total$</code>
SWAP 空闲：<code>$swap_free$</code>
SWAP 占用比：<code>$swap_percent$</code>

硬盘总读取：<code>$disk_read$</code>
硬盘总写入：<code>$disk_write$</code>
$disk_usage$

网络总发送：<code>$network_sent$</code>
网络总接收：<code>$network_received$</code>
```
