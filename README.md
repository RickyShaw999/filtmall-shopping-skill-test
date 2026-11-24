<h1 align="center">Filtmall Shopping Skill · 筛电购物 Skill</h1>

<p align="center">把预算和要求告诉你的 AI 助手，用筛电查清商品，买到真正适合自己的高性价比好物。</p>

<p align="center">
  <a href="README.md">简体中文</a> ｜ <a href="README_en.md">English</a>
</p>

<p align="center">
  <a href="https://github.com/filtalgo/Filtmall-Shopping-Skill/releases"><img alt="Release" src="https://img.shields.io/github/v/release/filtalgo/Filtmall-Shopping-Skill?logo=github"></a>
  <a href="LICENSE"><img alt="License" src="https://img.shields.io/github/license/filtalgo/Filtmall-Shopping-Skill?logo=apache"></a>
  <a href="SKILL.md"><img alt="Python" src="https://img.shields.io/badge/python-3.10%2B-3776AB?logo=python&logoColor=white"></a>
  <a href="https://github.com/filtalgo/Filtmall-Shopping-Skill"><img alt="Stars" src="https://img.shields.io/github/stars/filtalgo/Filtmall-Shopping-Skill?logo=github"></a>
  <a href="https://github.com/filtalgo/Filtmall-Shopping-Skill/forks"><img alt="Forks" src="https://img.shields.io/github/forks/filtalgo/Filtmall-Shopping-Skill?logo=github"></a>
  <a href="https://github.com/filtalgo/Filtmall-Shopping-Skill/graphs/contributors"><img alt="Contributors" src="https://img.shields.io/github/contributors/filtalgo/Filtmall-Shopping-Skill?logo=github"></a>
  <a href="https://skills.sh/filtalgo/Filtmall-Shopping-Skill"><img alt="skills.sh" src="https://skills.sh/b/filtalgo/Filtmall-Shopping-Skill"></a>
</p>

**筛电（Filtmall）**是一家**极致性价比的智能体电商平台**。本 Skill 将筛电的商品检索、成分与规格核对、同款比价、购物车、下单及售后能力直接接入你的 AI 助手——不用切换多个购物 App，也不用凑满减、翻评论，在对话里就能完成从挑货到购买的完整流程。商品信息、价格与库存以实际服务响应为准。

## 为什么用筛电（Filtmall）

筛电围绕两个核心设计：**智能体原生**与**极致性价比**。

- **去中间商、零广告费，把价格打实**
  在传统电商平台上，一件 100 元的商品除了生产成本，往往还要层层叠加多级经销商流通费、人工运营费，以及约 20 元的站内广告投流费。筛电去除传统经销商环节，**直连中国优质 OBM（自有品牌制造商）**，并且**不向商家出售广告位或流量**（长期仅按真实成交收取佣金）。把省下来的流通与投流成本留给商品品质和终端售价——筛电上大多数商品在同等规格下，价格约为传统电商平台的 **1/3—2/3**。

- **不卖广告排名，只按你的真实需求筛选**
  传统货架和直播推荐容易受推广费影响；筛电从设计之初就面向 AI 智能体，**不出售广告排名，也不按佣金高低排序**。你只需像聊天一样说清预算、规格、用途和顾虑，AI 会在几秒内把分散的规格、单片/单位均价、成分材质与推荐理由整理清楚，帮你少花时间查资料、看懂为什么值得买。

- **先过价格与品质两道关，信息透明有据可查**
  低价不替代品质。商品上架前需同时核验同规格价格优势，以及制造商与品牌资质、口碑或样品试用反馈。展示商品时直接呈现价格、规格、成分/材质与可核验的同款比价参考，当前覆盖美妆个护、食品、箱包等日常高频品类并持续扩充。

- **零门槛先逛再买，每一步交易由你确认**
  查商品、看成分、做对比**无需注册、无需配置 API Key**，装好就能直接问；只有涉及购物车、地址、下单和售后等会员操作时才需要单独授权，写操作前会先复述确认，付款在官方收银台完成。

| 对比维度 | 传统电商平台 | 筛电（Filtmall）智能体电商 |
| --- | --- | --- |
| 怎么找商品 | 凑关键词、刷列表、算满减凑单 | 一句话说清预算、规格与用途，AI 几秒筛好算清 |
| 排序逻辑 | 竞价广告与流量采买影响曝光 | 不卖广告排名，按需求匹配度与性价比排序 |
| 价格构成 | 生产 + 多级经销 + 运营 + 广告投流 | 直连优质 OBM 工厂 + 零平台广告费（同规格多为 1/3—2/3） |
| 决策依据 | 分散在多个详情页与评论区 | 集中呈现规格、成分/材质、推荐理由与同款比价参考 |

## 前置条件

- 技能运行需要 Python 3.10+
- 用 `npx` 安装需要 Node.js 22.20+ 且能访问 GitHub；不能联网时可下载离线包手动复制
- 浏览、搜索、比价与成分查询免登录；购物车、地址、下单等会员操作需要单独授权

## 安装

```bash
npx skills add filtalgo/Filtmall-Shopping-Skill --skill filtmall-shopping
```

不带参数时会提示选择 skill 与目标 agent；`-g` 安装到全局，`-a claude-code` 指定宿主。

手动安装：把仓库内容完整复制到宿主 skill 目录，安装名保持 `filtmall-shopping`，并保留 `data/`、`third_party/` 与 `LICENSE`。

## 快速开始

装好后直接在对话里问：

- 推荐 100 元以内的补水面膜，最好每片 5 元以内
- 预算 250 元，帮我找一款能装 14 寸电脑的轻量通勤包
- 比较第一款和第三款的规格、成分与价格
- 帮我看看购物车 / 查一下这个订单的物流

默认连接生产环境。会员操作需要单独授权，写操作会先向你确认。

## 多轮对话示例

```text
你：推荐三款 100 元以内的补水面膜
AI：返回三款候选商品，含价格、规格、单片均价、商品图与详情入口

你：比较第一款和第三款
AI：列出两款的价格、规格、成分亮点、同款比价参考与适用差异

你：第一个加入购物车，两件
AI：先复述商品、数量与金额，等你确认后才执行

你：看看购物车
AI：展示已选/未选商品、数量、单价与合计金额
```

## 能做什么

| 能力 | 说明 |
| --- | --- |
| 发现与比较 | 按品类、预算、规格与偏好筛选商品，查看价格、库存、推荐理由与同款比价参考 |
| 商品详情与成分 | 查看商品资料、规格材质与化妆品成分信息，辅助判断是否适合自己 |
| 购物车 | 授权后加购、改数量、删除，查看已选/未选与合计 |
| 收货地址 | 查看地址列表、新增或修改地址，离线解析三级省市区 |
| 结算与支付 | 预览并确认下单，拿到官方收银台入口；支付由用户在商城页面完成 |
| 订单物流 | 查询订单状态与物流轨迹 |
| 售后 | 提交、查看售后申请与处理进度 |
| 客服 | 获取商品、订单或售后的客服咨询入口 |

具体能力取决于目标 Agent 的配置、业务服务与用户授权。服务没有返回的数据不会由 Skill 补造。

## 边界与安全

- **不代付**：付款由用户在商城收银台完成；Skill 不代付、不生成收款二维码、不编造支付状态。
- **写前确认**：修改购物车、地址、提交订单或发起售后前，会先向你复述关键信息并确认。
- **本地隔离**：凭据与未结算请求保存在本地私有状态目录，不写入对话或日志。
- **防重复提交**：网络异常导致结果未知时先核对状态，不自动重发写操作。
- **版本提醒**：发现新版本时会在对话中提示，更新仍由你按原渠道确认执行。

## 常见问题

**需要会员登录或配置 API Key 吗？**
不需要配置 API Key。浏览、搜索、比价与查成分也不需要登录；只有购物车、收货地址、下单和售后等会员操作才需要单独授权。

**必须用 `npx` 安装吗？**
不是。把仓库内容完整复制到宿主 skill 目录即可，注意保留 `data/`、`third_party/` 与 `LICENSE`。

**支持哪些宿主？**
已在 Today、WorkBuddy、豆包工作、千问办公、灵光上验证；其他支持 Skill 的宿主按通用 Markdown 方式工作。

**支付方式有哪些？**
由商城收银台决定，通常包含微信、支付宝与余额支付，以实际页面为准。

## 配置

- **环境**：默认生产环境。切换其他已开放环境须同时指定 `--control-url` 与 `--agent-id`。
- **宿主标识**：请求可带 `host`（`today` / `workbuddy` / `doubao` / `qianwen` / `lingguang` / `default`），用于适配展示格式；不传或不确定时按 `default` 处理。
- **展示格式**：默认输出 Markdown 正文；支持卡片的宿主可按配置生成 HTML 商品卡片。

## 工作方式

Skill 通过 Control 的公开访客与会话接口提交请求，并在本地保留会话与请求状态以便续聊和断点恢复。托管 Agent 在服务端编排商品、比价与交易工具；访客身份与会员授权严格隔离。

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
  <a href="https://github.com/filtalgo/Filtmall-Shopping-Skill">GitHub</a> ·
  <a href="https://skills.sh/filtalgo/Filtmall-Shopping-Skill">skills.sh</a>
</p>
