---
title: AVATAR
summary: 介绍如何在自建时配置 SCP-079-AVATAR
type: docs
---

# AVATAR

本文介绍搭建 `SCP-079-AVATAR` 的注意事项，以及配置文件中各数值的意义。

请注意先参照[「通用步骤」](/general/)进行配置。

---

## 需要加入的频道

- SCP-079-HIDE
    - 必选
    - 应具有发送消息的权限

---

## 需要配合其他机器人使用

- SCP-079-REGEX
    - 推荐
- SCP-079-NOSPAM
    - 推荐

---

## 机器人性质

为 `User Bot`，需要使用一个通过手机号码注册的用户帐号。

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
    handlers.message

[proxy]
enabled = False
; 可根据需要自行决定是否使用 SOCKS5 代理
hostname = 127.0.0.1
port = 1080

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
nospam_id = [DATA EXPUNGED]
; SCP-079-NOSPAM 的 ID
tip_id = [DATA EXPUNGED]
; SCP-079-TIP 的 ID
user_id = [DATA EXPUNGED]
; SCP-079-USER 的 ID
warn_id = [DATA EXPUNGED]
; SCP-079-WARN 的 ID

[channels]
debug_channel_id = [DATA EXPUNGED]
; 此处填写调试频道 SCP-079-DEBUG 的 ID
hide_channel_id = [DATA EXPUNGED]
; 此处填写数据交换备份频道 SCP-079-HIDE 的 ID

[custom]
project_link = https://scp-079.org/avatar/
; 此处填写项目网址
project_name = SCP-079-AVATAR
; 此处填写项目名称

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

[language]
lang = cmn-Hans
; 此处填写 languages 文件夹下所包含的 YAML 文件的对应名称
normalize = True
; 此处填写 True 或 False，代表程序是否对消息文字进行转换处理

[limit]
limit_length = 30
; 此处填写整数，代表有效消息包含文本的最小长度
limit_message = 50
; 此处填写整数，代表用户加入白名单待选列表前，所需的有效发言的累计条数

[mode]
aio = False
; 此处填写 True 或 False，代表程序是否与其他程序共用同一机器人帐号
backup = False
; 此处填写 True 或 False，代表程序是否为备份副本

[time]
date_reset = 1st mon
; 此处填写每月重置数据的日期，例如 1st mon ，代表每月第一个星期一
time_begin = [DATA EXPUNGED]
; 此处填写 0 到 23 之间的整数，代表统计用户发言自定义时段的开始时间
time_check = [DATA EXPUNGED]
; 此处填写 0 到 23 之间的整数，代表每日自动生成全局白名单的时间点
time_end = [DATA EXPUNGED]
; 此处填写 0 到 23 之间的整数，代表统计用户发言自定义时段的结束时间
time_new = 1800
; 此处填写整数，代表判断用户为新用户的入群时长，用于进行头像复查，单位为秒
time_old = 7776000
; 此处填写整数，代表判断用户为老用户的入群时长，单位为秒
```
