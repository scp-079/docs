---
title: REGEX
summary: 介绍如何在自建时配置 SCP-079-REGEX
type: docs
---

# REGEX

本文介绍搭建 `SCP-079-REGEX` 的注意事项，以及配置文件中各数值的意义。

请注意先参照[「通用步骤」](/general/)进行配置。

---

## 需要加入的频道

- SCP-079-DEBUG
    - 必选
    - 应具有发送消息的权限
- SCP-079-EXCHANGE
    - 必选
    - 应具有发送消息的权限
- SCP-079-LOGGING
    - 必选
    - 应具有发送消息的权限
- SCP-079-CRITICAL
    - 应具有发送消息的权限
- SCP-079-HIDE
    - 应具有发送消息的权限

---

## 需要加入群组

- SCP-079-REGEX
    - 必选
    - 应具有管理员权限
- SCP-079-TEST
    - 必选
    - 应具有管理员权限

---

## 需要配合其他机器人使用

- SCP-079-USER
    - 必选
- SCP-079-NOSPAM
    - 推荐

---

## 机器人性质

为 `常规 Bot`，需要在 [BotFather](https://t.me/BotFather) 处获取 `bot token`。

---

## 文件 `config.ini`

> 这是一个自定义的文件。文件应位于 `config.ini.example` 同目录下。
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
    handlers.callback
    handlers.command
    handlers.message

[proxy]
enabled = False
; 可根据需要自行决定是否使用 SOCKS5 代理
hostname = 127.0.0.1
port = 1080

[basic]
bot_token = [DATA EXPUNGED]
; 此处填写在 @BotFather 处获得的 token
prefix = /!
; 命令前的可用字符，如在群组中使用非常规命令前缀，需要机器人有获取普通消息的权限

[channels]
critical_channel_id = [DATA EXPUNGED]
; 此处填写紧急频道 SCP-079-CRITICAL 的 ID
debug_channel_id = [DATA EXPUNGED]
; 此处填写调试频道 SCP-079-DEBUG 的 ID
exchange_channel_id = [DATA EXPUNGED]
; 此处填写数据交换频道 SCP-079-EXCHANGE 的 ID
hide_channel_id = [DATA EXPUNGED]
; 此处填写数据交换备份频道 SCP-079-HIDE 的 ID
regex_group_id = [DATA EXPUNGED]
; 此处填写操作群组 SCP-079-REGEX 的 ID
test_group_id = [DATA EXPUNGED]
; 此处填写测试群组 SCP-079-TEST 的 ID

[custom]
aio = False
; 此处填写 True 或 False，代表程序是否与其他程序共用同一机器人帐号
backup = False
; 此处填写 True 或 False，代表程序是否为备份副本
date_reset = 1st mon
; 此处填写每月重置数据的日期，例如 1st mon ，代表每月第一个星期一
limit_temp = 14
; 此处填写整数，代表 ban 类词组在多少天内不触发被自动移除
per_page = 10
; 每页显示的词组数量
project_link = https://scp-079.org/regex/
; 此处填写项目网址
project_name = SCP-079-REGEX
; 此处填写项目名称
zh_cn = True
; 此处填写 True 或 False，代表程序是否启用简体中文模式

[encrypt]
key = [DATA EXPUNGED]
; 各机器人加密字符串所用的统一密码，需由程序生成
password = [DATA EXPUNGED]
; 各机器人加密文件所用的统一密码，建议为长度 16 及以上的随机字符串
```
