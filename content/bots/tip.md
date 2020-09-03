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

- SCP-079-COMPROMISE
    - 必选
    - 应具有发送消息的权限
- SCP-079-DEBUG
    - 必选
    - 应具有发送消息的权限
- SCP-079-EXCHANGE
    - 必选
    - 应具有发送消息的权限
- SCP-079-LOGGING
    - 必选
    - 应具有发送消息的权限
- SCP-079-TIP
    - 必选
    - 应具有发送消息的权限
- SCP-079-CAPTCHA
    - 创建的公开频道，利用 TIP 绑定专用验证群组，在此生成加群链接
    - 应具有发送消息的权限
- SCP-079-CRITICAL
    - 应具有发送消息的权限
- SCP-079-HIDE
    - 应具有发送消息的权限

---

## 需要加入群组

- SCP-079-CAPTCHA
    - 此为 CAPTCHA 的专用验证群组
    - 应具有删除消息、邀请用户、置顶消息的管理员权限
- SCP-079-TEST
    - 应为群组管理员

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
compromise_channel_id = [DATA EXPUNGED]
; 此处填写频道 SCP-079-COMPROMISE 的 ID
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
tip_channel_id = [DATA EXPUNGED]
; 此处填写频道 SCP-079-TIP 的 ID

[custom]
default_group_link = https://t.me/SCP_079_DEBUG
; 此处填写 DEBUG 频道信息中默认的群组链接
leave_button = 申请使用
; 此处填写未授权使用时，发送说明消息的按钮文字
leave_link = https://scp-079.org/ApplyForUse/
; 此处填写未授权使用时，发送说明消息的按钮链接
leave_reason = 需要授权方可使用
; 此处填写未授权使用时，退出群组的原因
manual_link = https://manuals.scp-079.org/bots/tip/
; 此处填写使用手册的访问链接
project_link = https://scp-079.org/tip/
; 此处填写项目网址
project_name = SCP-079-TIP
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

[mode]
aio = False
; 此处填写 True 或 False，代表程序是否与其他程序共用同一机器人帐号
backup = False
; 此处填写 True 或 False，代表程序是否为备份副本

[time]
date_reset = 1st mon
; 此处填写每月重置数据的日期，例如 1st mon ，代表每月第一个星期一
time_channel = 3600
; 此处填写整数，代表入群频道中，群组链接的刷新时间间隔，单位为秒
time_keyword = 300
; 此处填写整数，代表无痕模式下自动回收关键词回复的时间，单位为秒
time_ot = 86400
; 此处填写整数，代表无痕模式下自动回收 OT 警告的时间，单位为秒
time_rm = 86400
; 此处填写整数，代表无痕模式下自动回收 RM 警告的时间，单位为秒
time_welcome = 180
; 此处填写整数，代表无痕模式下自动回收入群欢迎消息的时间，单位为秒
```

## 文件 `join.txt`

> 这是一个自定义的文件。文件应位于 `data/config/` 目录下，可参照 `examples/join.txt` 的格式进行设置。
>
> 此文件将作为机器人加入已授权群组后，其发送的提示消息。
>
> 当设定消息内容的样式时（链接、加粗、斜体、代码块），请内容遵从 HTML 格式，请见：<https://docs.pyrogram.org/topics/text-formatting#html-style>
>
> `join.txt` 文件支持设置消息按钮，添加按钮的方式为：
>
> 在文件尾部，使用一行 6 个 `+` 号作为分隔线，来区分正文与按钮部分。在分隔线后方，每行都将代表一个按钮配置，对于每个按钮配置，请使用双竖线 `||` 分隔按钮文字（前）和按钮链接（后），最多可设置共 6 个按钮。可参考示例部分。
>
> 此文件的内容可自由编写，但请注意保证文本不超过 4096 个字符。

> 以下是示例，仅供参考：

```
欢迎使用本机器人，请您查看使用手册。

++++++

使用手册 || https://manuals.scp-079.org/bots/tip/
```

## 文件 `start.txt`

> 这是一个自定义的文件。文件应位于 `data/config/` 目录下，可参照 `examples/start.txt` 的格式进行设置。
>
> 此文件将作为用户私聊发送 `/start` 命令给机器人时，机器人所发送的消息内容。
>
> 当设定消息内容的样式时（链接、加粗、斜体、代码块），请内容遵从 HTML 格式，请见：<https://docs.pyrogram.org/topics/text-formatting#html-style>
>
> `start.txt` 文件支持设置消息按钮，添加按钮的方式为：
>
> 在文件尾部，使用一行 6 个 `+` 号作为分隔线，来区分正文与按钮部分。在分隔线后方，每行都将代表一个按钮配置，对于每个按钮配置，请使用双竖线 `||` 分隔按钮文字（前）和按钮链接（后），最多可设置共 6 个按钮。可参考示例部分。
>
> 此文件的内容可自由编写，但请注意保证文本不超过 4096 个字符。

> 以下是示例，仅供参考：

```
本机器人功能及特性：

★ 所有自定义的回复消息，均可设置多个包含链接的按钮。
★ 所有回复消息，都默认采取定时回收机制，不干扰群组内消息流。
★ 可发送自定义的入群欢迎消息，并默认只在用户通过 CAPTCHA 入群验证后才发送欢迎消息。
★ 群组可自定义多个关键词回复。
★ 具体关键词的回复可单独自定义触发时采取的操作，例如：仅发送预设回复消息、删除原消息、移除用户、禁言用户（可自定义时长）、封禁用户（可自定义时长）。
★ 具体关键词的回复可单独自定义何人可触发，例如：普通成员、管理员、所有人。
★ 具体关键词的回复可单独自定义判断触发的多种模式，例如：包含匹配、全匹配、大小写敏感、仅对用户名和转发来源名触发、过滤名称内干扰符号、仅对转发的消息触发。
★ 具体关键词的回复可单独自定义销毁时间。
★ 支持用户点击消息按钮后，机器人自动发送群组预设消息。
★ 对于自定义关键词，将保留触发的统计数据以供查询。
★ 采取频率限制机制，避免关键词被群员试探大量触发而造成刷屏。
★ 保持或取消群组内的置顶。
★ 自定义离题警告。
★ 自定义判断并触发 RM 笑话警告。
★ 可设置群组绑定公开频道，在其中提供定时刷新的私有群组的入群链接。

<b>温馨提示：</b>如果本机器人（SCP-079-TIP）「触发了任何关键词回复，删除了某条用户发送的消息，或者禁言、封禁了某个用户」，则机器人完全是按照群组的自定义关键词的设置进行操作的，与机器人本身的全局规则没有任何关系，全部属于群组自己设置的预期行为，因此也绝对不是所谓的「机器人误判」。因此如您有任何异议，您应该联系所在群组的管理员，而不是本项目工作组。

点击下方按钮了解更多。

++++++

文档 || https://scp-079.org/tip/
源码 || https://github.com/scp-079/scp-079-tip/
申请使用 || https://scp-079.org/ApplyForUse/
提交需求 || https://github.com/scp-079/scp-079-tip/issues
更多功能 || https://scp-079.org/bots/
```
