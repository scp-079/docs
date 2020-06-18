---
title: TIP
summary: 介绍如何在自建时配置 SCP-079-TIP
type: docs
---

# TIP

本文介绍搭建 `SCP-079-TIP` 的注意事项，以及配置文件中各数值的意义。

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
- SCP-079-CAPTCHA
    - 创建的公开频道，利用 TIP 绑定专用验证群组，在此生成加群链接
    - 应具有发送消息的权限
- SCP-079-CRITICAL
- SCP-079-HIDE

---

## 需要加入群组

- SCP-079-CAPTCHA
    - 此为 CAPTCHA 的专用验证群组
    - 应具有删除消息、邀请用户、置顶消息的管理员权限
- SCP-079-TEST

---

## 需要配合其他机器人使用

- SCP-079-USER
    - 必选
- SCP-079-CAPTCHA
    - 推荐
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
prefix = /!

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
project_link = https://scp-079.org/tip/
; 此处填写项目网址
project_name = SCP-079-TIP
; 此处填写项目名称
time_channel = 3600
; 此处填写整数，代表入群频道中，群组链接的刷新时间间隔，单位为秒
time_keyword = 300
; 此处填写整数，代表无痕模式下自动回收关键词回复的时间，单位为秒
time_ot = 86400
; 此处填写整数，代表无痕模式下自动回收 OT 警告的时间，单位为秒
time_rm = 300
; 此处填写整数，代表无痕模式下自动回收 RM 警告的时间，单位为秒
time_welcome = 180
; 此处填写整数，代表无痕模式下自动回收入群欢迎消息的时间，单位为秒
zh_cn = True
; 此处填写 True 或 False，代表程序是否启用简体中文模式

[emoji]
emoji_ad_single = 15
; 此处填写整数，代表多少个同样的 emoji 在消息中出现则被认为是 ad_ 类词组
emoji_ad_total = 30
; 此处填写整数，代表一共多少个 emoji 在消息中出现则被认为是 ad_ 类词组
emoji_many = 15
; 此处填写整数，代表多少个 emoji 在消息中出现则被认为该消息含有多个 emoji
emoji_protect = \U0001F642
; 此处填写字符串，其中包含的 emoji 将受到保护，不计入各类判断中，字符串中间无空格，请以 \UXXXXXXXX 的形式代表一个 emoji
emoji_wb_single = 10
; 此处填写整数，代表多少个同样的 emoji 在消息中出现则被认为是 wb 类词组
emoji_wb_total = 15
; 此处填写整数，代表一共多少个 emoji 在消息中出现则被认为是 wb 类词组

[encrypt]
key = [DATA EXPUNGED]
; 各机器人加密字符串所用的统一密码，需由程序生成
password = [DATA EXPUNGED]
; 各机器人加密文件所用的统一密码，建议为长度 16 及以上的随机字符串
```
