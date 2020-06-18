---
title: ID
summary: 介绍如何在自建时配置 SCP-079-ID
type: docs
---

# ID

本文介绍搭建 `SCP-079-ID` 的注意事项，以及配置文件中各数值的意义。

请注意先参照[「通用步骤」](/general/)进行配置。

---

## 需要加入的群组

- SCP-079-TEST
    - 可选

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

[channels]
test_group_id = 0
; 此处填写测试群组 SCP-079-TEST 的 ID

[language]
lang = cmn-Hans
; 此处填写 languages 文件夹下所包含的 YAML 文件的对应名称

[mode]
aio = False
; 此处填写 True 或 False，代表程序是否与其他程序共用同一机器人帐号
```

---

## 文件 `start.txt`

> 这是一个自定义的文件。文件应位于 `start.txt.example` 同目录下。
>
> 此文件将作为用户私聊发送 `/start` 命令给机器人时，机器人所发送的消息内容。
>
> 当设定消息内容的样式时（链接、加粗、斜体、代码块），请内容遵从 HTML 格式，请见：<https://docs.pyrogram.org/topics/text-formatting#html-style>
>
> 此文件的内容可自由编写，但请注意保证文本不超过 4096 个字符。

> 以下是示例，仅供参考：

```
本机器人可协助您获取用户、群组、频道的 ID。

<code>------------------------</code>

<b>使用命令：</b>

<code>/id</code> - 在群组中发送此命令，将获得您的用户 ID，群组 ID
<code>/id</code> - 在群组中以回复用户消息的形式发送此命令，将获得您的用户 ID，被回复的用户 ID，和群组 ID
<code>/id</code> - 在本对话中发送此命令，将获得您的用户 ID
<code>/id @username</code> - 在本对话中发送此命令，将获得 <code>@username</code> 的 ID

<code>------------------------</code>

<b>转发消息：</b>

<code>转发频道消息到本对话中</code> - 将获得该频道的 ID
<code>转发用户消息到本对话中</code> - 将获得该用户的 ID

<code>------------------------</code>

当检查群组和频道的 ID 时，还将同时检查群组或频道是否收到 Telegram 限制，如果受限，将同时显示受限理由等信息。
```
