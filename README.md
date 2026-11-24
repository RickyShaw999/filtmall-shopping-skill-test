# Filtmall Shopping Skill

在对话里完成选品、比价、加购、下单与售后跟进的托管购物技能。

[![License](https://img.shields.io/github/license/filtalgo/Filtmall-Shopping-Skill?style=for-the-badge)](LICENSE)
[![Release](https://img.shields.io/github/v/release/filtalgo/Filtmall-Shopping-Skill?style=for-the-badge)](https://github.com/filtalgo/Filtmall-Shopping-Skill/releases)
[![Python](https://img.shields.io/badge/python-3.10%2B-blue?style=for-the-badge)](SKILL.md)
[![Stars](https://img.shields.io/github/stars/filtalgo/Filtmall-Shopping-Skill?style=for-the-badge)](https://github.com/filtalgo/Filtmall-Shopping-Skill)
[![skills.sh](https://skills.sh/b/filtalgo/filtmall-shopping-skill?style=for-the-badge)](https://skills.sh/filtalgo/filtmall-shopping-skill)

## 前置条件

- 技能运行需要 Python 3.10+
- 用 `npx` 安装需要 Node.js 22.20+ 且能访问 GitHub；不能联网时用离线包手动复制
- 会员相关操作需要用户单独授权

## 安装

```bash
npx skills add filtalgo/filtmall-shopping-skill --skill filtmall-shopping
```

不带参数时会提示选择 skill 与目标 agent；`-g` 安装到全局，`-a claude-code` 指定宿主。

手动安装：把仓库内容完整复制到宿主 skill 目录，安装名保持 `filtmall-shopping`，并保留 `data/`、`third_party/` 与 `LICENSE`。

## 快速开始

装好后直接在对话里问：

- 推荐 100 元以内的保湿面膜
- 比较第一款和第三款的规格与价格
- 帮我看看购物车
- 查一下这个订单的物流

默认连接生产环境。会员操作需要单独授权，写操作会先向你确认。

## 能做什么

| 能力         | 说明                                               |
| ------------ | -------------------------------------------------- |
| 发现与比较   | 描述需求找商品，查看价格、规格、库存与比价证据     |
| 详情与客服   | 打开商城详情页，或获取客服咨询入口                 |
| 购物车与地址 | 授权后管理购物车与收货地址                         |
| 结算与跟进   | 预览并确认下单，拿到收银台入口；查订单、物流与售后 |

## 工作方式

Skill 通过 Control 的公开访客与会话接口，把请求委托给服务端托管购物 Agent，再读取结构化结果展示。访客身份不等于会员授权。

## 边界

- 付款由用户在商城收银台完成；Skill 不代付、不生成二维码、不编造支付状态。
- 修改购物车、地址、订单或发起售后前，会先与用户确认。
- 凭据与未结算请求保存在本地私有状态目录，不写入对话或日志。
- 发现新版本时会在对话中提示，安装仍需按原渠道手动替换。

## 文档

- [SKILL.md](SKILL.md)：宿主调用与交互规则
- [references/protocol.md](references/protocol.md)：公开接口协议
- [references/presentation.md](references/presentation.md)：展示与宿主适配

## 许可证

[Apache-2.0](LICENSE)
