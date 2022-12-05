# @kivibot/core

[![npm (scoped)](https://img.shields.io/npm/v/@kivibot/core?color=527dec&label=%40kivibot%2Fcore&style=flat-square)](https://www.npmjs.com/package/@kivibot/core)
[![dm](https://shields.io/npm/dm/@kivibot/core?style=flat-square)](https://www.npmjs.com/package/@kivibot/core)
[![node engine](https://img.shields.io/node/v/@kivibot/core/latest.svg?style=flat-square)](https://nodejs.org)
[![discord](https://img.shields.io/static/v1?label=chat&message=on%20discord&color=7289da&logo=discord&style=flat-square)](https://discord.gg/RegGQD3Fu6)

> `@kivibot/core` is the core library of `KiviBot`.

KiviBot is a lightweight cross-platform Tencent QQ robot frame, powered by `Node.js` & `oicq2`. It is still in the test stage, and there may be many bugs. Documentation for it is also being improved, so stay tuned. Head to official documentation for more details: [KiviBot Beta Documentation (WIP)](https://beta.kivibot.com/)

## 介绍

`KiviBot` 是使用 [TypeScript](https://www.typescriptlang.org/) 编写的**轻量**、**跨平台**的 QQ 机器人框架。

框架提供了完备的状态监控、插件管理（支持热更新）、主副管理员机制、消息通知、请求处理功能以及友好的脚手架，开箱即用。框架完全开源，可扩展性强，插件开发简单，核心底层协议使用 [oicq2](https://github.com/takayama-lily/oicq)，API 众多，功能强大。另外，框架使用 [node](https://nodejs.org/) 驱动，得益于 `node` 及其高效的 `v8` 引擎，框架性能可观。

本项目开发初衷在于提高群活跃氛围、方便群管理，仅供个人娱乐、学习和交流使用，**不得将本项目用于任何非法用途**。

## 为什么选择 `KiviBot`

- 🚲 **轻量**: 无需运行 UI 界面，内存占用低，约 30-100 MB（取决于设备、群聊数和活跃程度）。

- ⚡ **高效**: 框架开发语言和底层协议语言一致，框架依赖少，执行效率高。

- 📦 **便携**: 使用 QQ 消息控制机器人，无需远程连接服务器进行操作，快速方便。

- 📱 **跨平台**: 不仅 Windows，Linux 能运行，手机和平板 (通过模拟 Linux 环境) 也能运行。

- 🔗 **多协议**: 支持安卓手机、安卓平板、iPad、安卓手表和 MacOS 协议。

- 🚤 **极速开发**: 学习门槛低，只需几行 JS/TS 代码就能编写插件。

- 💻 **开发者友好**: 插件支持热重载，拥有友好的脚手架与完备的 TS 类型定义。

更多特征等你探索...

## 插件示例

仅需编写少量 JavaScript 代码即可实现丰富功能，只要你有 JavaScript 语言的基础，上手开发一个插件是非常简单的。参考下面给出的比较完善的插件 Demo。

```js
const { KiviPlugin, segment, http } = require('@kivibot/core')

const plugin = new KiviPlugin('demo', '0.1.0')

plugin.onMounted(() => {
  plugin.onMessage(event => {
    const { raw_message } = event

    if (raw_message === 'hello') {
      const msgs = [segment.face(66), 'world']
      event.reply(msgs)
    }
  })
})

module.exports = { plugin }

```
