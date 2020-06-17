---
title: SCP-079
type: docs
---

# 自建说明书

{{< columns >}}
## 所需做的准备

SCP-079 系列机器人的搭建涉及多个频道、群组、机器人帐号、用户帐号的创建。本页面将对自建完整实例的所需要的频道、群组、帐号进行说明。当然，您可根据所需要的功能只自行搭建某一个或某几个机器人，此时则可对照各机器人单独的介绍页面来创建频道、群组等。

<--->

## 一些建议

自建机器人的昵称或 `username` 中请至少包含该项目代号，利于交流讨论。另外，Telegram 对机器人、频道、群组的创建有频率限制，遇到限制时，可切换多个用户帐号进行创建。
{{< /columns >}}

---

## 公开频道

本项目完整实例所需的公开频道有：

- [SCP-079-CAPTCHA](https://t.me/SCP_079_CAPTCHA)
    - 此频道用于 CAPTCHA 机器人在某些特殊情况下的引用
    - 频道中应提供一个消息，其中包含链接，链接为 CAPTCHA 的专用验证群组的邀请链接，此链接可使用 TIP 的「入群频道」功能生成，以保持定时刷新链接的特性
- [SCP-079-CONFIG](https://t.me/SCP_079_CONFIG)
    - 此频道用于 CONFIG 机器人在非私聊的模式下提供设置会话
- [SCP-079-CRITICAL](https://t.me/SCP_079_CRITICAL)
    - 此频道用于 STATUS 机器人更新各节点服务器的状态
    - 其他各主要 Bot 也应加入此频道，用于汇报各种突发情况
- [SCP-079-DEBUG](https://t.me/SCP_079_DEBUG)
    - 此频道用于各主要 Bot 在其中发送日志记录
- [SCP-079-ERROR](https://t.me/SCP_079_ERROR)
    - 此频道用于存放因机器人自动识别而产生的误判
- [SCP-079-LOGGING](https://t.me/SCP_079_LOGGING)
    - 此频道用于存放各种操作证据和消息存档

---

## 私有频道

本项目完整实例所需的私有频道有：

- **SCP-079-EXCHANGE**
    - 此频道用于各 Bot 之间进行数据交换
- **SCP-079-HIDE**
    - 此频道用于非匿名 Bot 和匿名 Bot 之间的数据交换
    - 当 EXCHANGE 频道因某种意外失效后，所有 Bot 会将数据交换操作自动转移至此频道
- **SCP-079-M**
    - 此频道用于记录 MANAGE 专用群组中的命令，作为证据存档
- **SCP-079-WATCH**
    - 此频道用于记录令 WATCH 触发追踪操作的消息

{{< hint warning >}}
**警告**  
以上频道如被设置为公开频道，则可能会给服务运行带来一些影响，或者有用户隐私泄露的风险。
{{< /hint >}}

---

## 私有群组

本项目完整实例所需的私有群组有：

- **SCP-079-CAPTCHA**
    - 此群组用于 CAPTCHA 机器人的专用验证群组
- **SCP-079-MANAGE**
    - 此群组用于工作组团队的日常操作
- **SCP-079-REGEX**
    - 此群组用于维护正则表达式
- **SCP-079-TEST**
    - 此群组用于测试各 Bot 对消息的检测结果，或者检查机器人运行状态
- **SCP-079-TICKET**
    - 此群组用于工作组团队处理来自用户的私聊

{{< hint danger >}}
**注意**  
以上群组如被设置为公开群组，则可能给服务运行带来严重影响，甚至可能会令使用服务的用户群组遭到恶意破坏。
{{< /hint >}}

---

## 常规 Bot

本项目完整实例所需的常规 Bot 有：

- SCP-079-CAPTCHA
- SCP-079-CLEAN
- SCP-079-CONFIG
- SCP-079-HIDE
- SCP-079-LANG
- SCP-079-LONG
- SCP-079-MANAGE
- SCP-079-NOFLOOD
- SCP-079-NOPORN
- SCP-079-NOSPAM
- SCP-079-PM
- SCP-079-REGEX
- SCP-079-STATUS
- SCP-079-TICKET
- SCP-079-WARN

---

## User Bot

本项目完整实例所需的 User Bot 有：

- SCP-079-AVATAR
- SCP-079-USER
- SCP-079-WATCH

{{< details "什么是 User Bot？" >}}
所谓 User Bot，就是使用正常 Telegram 人类帐号工作的机器人。
{{< /details >}}

{{< hint info >}}
**提示**  
对于所有在群组中工作的机器人来说，SCP-079-USER 是工作核心，它们都要求 SCP-079-USER 在群组内协助工作。
{{< /hint >}}
