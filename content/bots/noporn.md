---
title: NOPORN
summary: 介绍如何在自建时配置 SCP-079-NOPORN
type: docs
---

# NOPORN

本文介绍搭建 `SCP-079-NOPORN` 的注意事项，以及配置文件中各数值的意义。

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

- SCP-079-TEST
    - 应具有管理员权限

---

## 需要配合其他机器人使用

- SCP-079-USER
    - 必选
- SCP-079-REGEX
    - 推荐
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

[bots]
avatar_id = [DATA EXPUNGED]
; SCP-079-AVATAR 的 ID
captcha_id = [DATA EXPUNGED]
; SCP-079-CAPTCHA 的 ID
clean_id = [DATA EXPUNGED]
; SCP-079-CLEAN 的 ID
index_id = [DATA EXPUNGED]
; SCP-079-INDEX 的 ID
lang_id = [DATA EXPUNGED]
; SCP-079-LANG 的 ID
long_id = [DATA EXPUNGED]
; SCP-079-LONG 的 ID
noflood_id = [DATA EXPUNGED]
; SCP-079-NOFLOOD 的 ID
noporn_id = [DATA EXPUNGED]
; SCP-079-NOPORN 的 ID
recheck_id = 1
nospam_id = [DATA EXPUNGED]
; SCP-079-NOSPAM 的 ID
tip_id = [DATA EXPUNGED]
; SCP-079-TIP 的 ID
user_id = [DATA EXPUNGED]
; SCP-079-USER 的 ID
warn_id = [DATA EXPUNGED]
; SCP-079-WARN 的 ID

[channels]
critical_channel_id = [DATA EXPUNGED]
; 此处填写紧急频道 SCP-079-CRITICAL 的 ID
debug_channel_id = [DATA EXPUNGED]
; 此处填写调试频道 SCP-079-DEBUG 的 ID
exchange_channel_id = [DATA EXPUNGED]
; 此处填写数据交换频道 SCP-079-EXCHANGE 的 ID
hide_channel_id = [DATA EXPUNGED]
; 此处填写数据交换备份频道 SCP-079-HIDE 的 ID
logging_channel_id = [DATA EXPUNGED]
; 此处填写证据存放频道 SCP-079-LOGGING 的 ID
test_group_id = [DATA EXPUNGED]
; 此处填写测试群组 SCP-079-TEST 的 ID

[custom]
aio = False
; 此处填写 True 或 False，代表程序是否与其他程序共用同一机器人帐号
backup = False
; 此处填写 True 或 False，代表程序是否为备份副本
date_reset = 1st mon
; 此处填写每月重置数据的日期，例如 1st mon ，代表每月第一个星期一
default_group_link = https://t.me/SCP_079_DEBUG
; 此处填写 DEBUG 频道信息中默认的群组链接
image_size = 2097152
; 此处填写整数，代表分析图片文档的最大大小，超过此大小则不通过下载原文件进行分析，单位为 B
invalid = admin admins BotFather gamebot gif SpamBot Stickers telegram vote
; 此处填写不被机器人认为是 Telegram 链接的 username ，用空格分隔，无 @ 前缀
limit_track = 8
; 此处填写整数，代表用户短时间内加入多少群组才被认为是需要特殊对待的用户
project_link = https://scp-079.org/noporn/
; 此处填写项目网址
project_name = SCP-079-NOPORN
; 此处填写项目名称
threshold_porn = 0.8
; 此处填写 0 到 1 的小数，建议为 0.7 以上
time_ban = 10800
; 建议追踪封禁状态维持的时间，单位为秒
time_new = 1800
; 此处填写整数，代表判断用户为新用户的入群时长，单位为秒
time_punish = 60
; 惩罚用户的时间，期间用户发送的所有消息将被删除，并且，在此期间内若其发送消息将重新计时
time_short = 300
; 此处填写整数，代表判断用户为刚刚入群的入群时长，用户在群组开启新用户限制时使用，单位为秒
time_track = 3600
; 此处填写整数，代表用户在多短时间内加入多个群组才被认为是需要特殊对待的用户
zh_cn = True
; 此处填写 True 或 False，代表程序是否启用简体中文模式

[encrypt]
key = [DATA EXPUNGED]
; 各机器人加密字符串所用的统一密码，需由程序生成
password = [DATA EXPUNGED]
; 各机器人加密文件所用的统一密码，建议为长度 16 及以上的随机字符串
```
