<h1 align="center">Filtmall Shopping Skill</h1>

<p align="center">在对话里完成选品、比价、加购、下单与售后跟进的托管购物技能。</p>

<p align="center">
  <a href="README.md">简体中文</a> ｜ <a href="README_en.md">English</a>
</p>


<p align="center">
  <a href="https://github.com/filtalgo/filtmall-shopping-skill/releases"><img alt="Release" src="https://img.shields.io/github/v/release/filtalgo/filtmall-shopping-skill?logo=github"></a>
  <a href="LICENSE"><img alt="License" src="https://img.shields.io/github/license/filtalgo/filtmall-shopping-skill?logo=apache"></a>
  <a href="SKILL.md"><img alt="Python" src="https://img.shields.io/badge/python-3.10%2B-3776AB?logo=python&logoColor=white"></a>
  <a href="https://github.com/filtalgo/filtmall-shopping-skill"><img alt="Stars" src="https://img.shields.io/github/stars/filtalgo/filtmall-shopping-skill?logo=github"></a>
  <a href="https://github.com/filtalgo/filtmall-shopping-skill/forks"><img alt="Forks" src="https://img.shields.io/github/forks/filtalgo/filtmall-shopping-skill?logo=github"></a>
  <a href="https://github.com/filtalgo/filtmall-shopping-skill/graphs/contributors"><img alt="Contributors" src="https://img.shields.io/github/contributors/filtalgo/filtmall-shopping-skill?logo=github"></a>
  <a href="https://skills.sh/filtalgo/filtmall-shopping-skill"><img alt="skills.sh" src="https://skills.sh/b/filtalgo/filtmall-shopping-skill"></a>
</p>


Filtmall Shopping 是筛电的托管购物 Agent Skill。用户在对话里描述需求，Skill 把请求委托给服务端的购物 Agent，再把商品、价格、库存和各类购物状态整理成可读结果返回。商品信息、价格与库存以实际服务响应为准。

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

## 多轮对话示例

```
你：推荐三款 100 元以内的补水面膜
AI：三款商品，含价格、规格、商品图与详情入口

你：比较第一款和第三款
AI：两款的价格、规格、评分与差异

你：第一个加入购物车，两件
AI：先复述商品、数量与金额，确认后才执行

你：看看购物车
AI：已选/未选商品、数量、单价与合计
```

## 能做什么

| 能力       | 说明                                                         |
| ---------- | ------------------------------------------------------------ |
| 发现与比较 | 描述品类、预算与偏好找商品，查看价格、规格、库存、推荐理由与比价证据 |
| 商品详情   | 查看商品资料、规格与成分信息                                 |
| 购物车     | 授权后加购、改数量、删除，查看已选/未选与合计                |
| 收货地址   | 查看地址列表、新增或修改地址，离线解析三级省市区             |
| 结算与支付 | 预览并确认下单，拿到收银台入口；支付由用户在商城页面完成     |
| 订单物流   | 查询订单状态与物流轨迹                                       |
| 售后       | 提交、查看售后申请与处理进度                                 |
| 客服       | 获取商品、订单或售后的客服咨询入口                           |

具体能力取决于目标 Agent 的配置、业务服务与用户授权。服务没有返回的数据不会由 Skill 补造。

## 配置

- **环境**：默认生产环境。切换其他已开放环境须同时指定 `--control-url` 与 `--agent-id`。
- **宿主标识**：请求可带 `host`（`today` / `workbuddy` / `doubao` / `qianwen` / `lingguang`），用于适配展示格式；不传则按默认处理。
- **展示格式**：默认输出 Markdown 正文；支持卡片的宿主可生成 HTML 商品卡片。

## 工作方式

Skill 通过 Control 的公开访客与会话接口提交请求，并保留会话与请求状态以便续聊和恢复。托管 Agent 在服务端编排业务工具；访客身份不等于会员授权。

## 边界与安全

- 付款由用户在商城收银台完成；Skill 不代付、不生成二维码、不编造支付状态。
- 修改购物车、地址、订单或发起售后前，会先与用户确认。
- 凭据与未结算请求保存在本地私有状态目录，不写入对话或日志。
- 结果未知时先核对状态，不自动重发写操作。
- 发现新版本时会在对话中提示，安装仍需按原渠道手动替换。

## 常见问题

**需要会员登录吗？**
浏览和查商品不需要；购物车、地址、下单等会员操作需要单独授权。

**必须用 `npx` 安装吗？**
不是。把仓库内容完整复制到宿主 skill 目录即可，注意保留 `data/` 与 `third_party/`。

**支持哪些宿主？**
已在 Today、WorkBuddy、豆包工作、千问办公、灵光上验证；其他宿主按通用 Markdown 方式工作。

**支付方式有哪些？**
由商城收银台决定，通常包含微信、支付宝与余额支付，以实际页面为准。

## 目录结构

```text
SKILL.md                    # 宿主调用与交互规则
references/                 # 展示、授权、恢复、地址、维护与接口协议
scripts/service.py          # 单次调用与常驻服务入口
scripts/hosts.py            # 宿主枚举与展示策略
data/                       # 生产与预发地区数据快照
third_party/                # 离线号码库与许可证
tests/                      # 离线测试
```

## 开发与测试

```bash
python3 -m unittest discover -s tests
node tooling/skills/validate-skill-packages.js
```

## 文档

- [SKILL.md](SKILL.md)：宿主调用与交互规则
- [references/protocol.md](references/protocol.md)：公开接口协议
- [references/presentation.md](references/presentation.md)：展示与宿主适配
- [references/authorization.md](references/authorization.md)：授权、下单确认与支付边界

## 许可证

[Apache-2.0](LICENSE)

---

<p align="center">
  <a href="https://www.filtalgo.com/">筛电官网</a> ·
  <a href="https://github.com/filtalgo/filtmall-shopping-skill">GitHub</a> ·
  <a href="https://skills.sh/filtalgo/filtmall-shopping-skill">skills.sh</a>
</p>

