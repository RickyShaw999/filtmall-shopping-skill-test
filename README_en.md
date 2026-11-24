<h1 align="center">Filtmall Shopping Skill</h1>

<p align="center">Tell your AI assistant your budget and requirements — research products clearly and buy high-value goods directly through Filtmall.</p>

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

**Filtmall (筛电)** is an **agent-native e-commerce platform built for extreme value-for-money**. This Skill brings Filtmall's product discovery, spec & ingredient checks, price comparison, cart, checkout, and after-sales workflows straight into your AI assistant. Product details, prices, and inventory are determined by live service responses.

## Why Filtmall

Filtmall is built around two core principles: **Agent-Native** and **Extreme Value-for-Money**.

- **Factory-direct OBM supply, zero platform ad fees**
  On traditional e-commerce platforms, a ¥100 item often carries multi-layer distributor markups, store operation overhead, and roughly ¥20 in paid ad traffic on top of manufacturing cost. Filtmall removes traditional middlemen by connecting directly with vetted **OBMs (Original Brand Manufacturers)** and **charges zero advertising or paid-traffic fees** (long-term revenue comes solely from transaction commissions). Most products on Filtmall are priced at roughly **1/3 to 2/3** of comparable specifications on traditional platforms.

- **No paid rankings — matched purely to your requirements**
  Filtmall never sells ad placements or ranks products by commission rate. State your budget, specs, use case, and constraints in plain language; your AI assistant gathers specs, unit prices, ingredients/materials, and clear reasons why each option fits in seconds.

- **Curated for both price and quality, with verifiable details**
  Products are vetted for both same-spec price advantage and manufacturer qualification, reputation, or sample feedback before listing. Results present transparent specs, ingredients, and verifiable price-comparison references across everyday categories such as beauty & personal care, food, and bags.

- **Zero-friction browsing, explicit confirmation on every transaction**
  No registration or API keys are required to browse, search, or compare. Member actions (cart, address, checkout, after-sales) require separate authorization, every write action asks for confirmation first, and payment happens on the official checkout page.

| Dimension | Traditional E-Commerce | Filtmall (Agent-Native) |
| --- | --- | --- |
| Discovery | Keyword guessing, endless scrolling, coupon math | Describe budget & needs in one sentence; AI filters and calculates in seconds |
| Ranking | Influenced by paid ads and traffic bidding | Zero paid rankings — sorted by requirement fit and value |
| Cost Structure | Manufacturing + distributors + ops + ad spend | Direct OBM manufacturers + zero platform ad fees (~1/3–2/3 typical price for same specs) |
| Decision Basis | Scattered product pages and noisy reviews | Consolidated specs, ingredients/materials, fit reasons, and price references |

## Prerequisites

- Python 3.10+
- Node.js 22.20+ with GitHub access for `npx` installation (or copy the full directory manually for offline use)
- Browsing, search, and ingredient lookups require no login; member operations require separate authorization

## Installation

```bash
npx skills add filtalgo/Filtmall-Shopping-Skill --skill filtmall-shopping
```

Run without flags to pick the skill and target agent interactively; pass `-g` for global installation or `-a claude-code` to target a specific host.

Manual installation: copy the entire repository into your host's skill directory as `filtmall-shopping`, preserving `data/`, `third_party/`, and `LICENSE`.

## Quick Start

Once installed, try asking in chat:

- Recommend moisturizing face masks under ¥100, ideally under ¥5 per sheet
- Find a lightweight commuter backpack under ¥250 that fits a 14-inch laptop
- Compare the specs, ingredients, and prices of the first and third options
- Show my shopping cart / Check the shipping status of this order

Connects to the production environment by default.

## Capabilities

| Capability | Description |
| --- | --- |
| Discovery & Comparison | Filter by category, budget, specs, and preferences; view prices, stock, fit reasons, and price references |
| Details & Ingredients | Inspect product specs, materials, and cosmetic ingredient details |
| Shopping Cart | Add, update quantity, remove items, and review totals after authorization |
| Shipping Addresses | List, add, or edit addresses with offline province/city/district resolution |
| Checkout & Payment | Preview and confirm orders to obtain the official checkout link; payment completes on the store page |
| Orders & Shipping | Track order status and delivery updates |
| After-Sales & Support | Submit/track after-sales requests and access customer support links |

Available capabilities depend on the target Agent configuration, business services, and user authorization. The Skill never fabricates unreturned data.

## Boundaries & Safety

- **No autonomous payment**: Payment is always completed by the user on the official checkout page.
- **Confirm before writes**: Cart, address, order, and after-sales changes always summarize key details and ask for confirmation first.
- **Local isolation**: Credentials and pending states are kept in a private local state directory and never written to chat or logs.
- **Idempotent recovery**: On uncertain network outcomes, the Skill checks status first rather than blindly re-sending write requests.

## Configuration & Testing

- **Environment**: Production by default. Pass both `--control-url` and `--agent-id` to switch to another open environment.
- **Host identifier**: Supports `host` values `today` / `workbuddy` / `doubao` / `qianwen` / `lingguang` / `default`.
- **Offline tests**:

```bash
python3 -m unittest discover -s tests
```

## Documentation

- [SKILL.md](SKILL.md): Host invocation and interaction rules
- [references/protocol.md](references/protocol.md): Public API protocol
- [references/presentation.md](references/presentation.md): Display and host adaptation
- [references/authorization.md](references/authorization.md): Authorization, confirmation, and payment boundaries

## License

[Apache-2.0](LICENSE)

---

<p align="center">
  <a href="https://www.filtalgo.com/">Filtalgo Website</a> ·
  <a href="https://github.com/filtalgo/Filtmall-Shopping-Skill">GitHub</a> ·
  <a href="https://skills.sh/filtalgo/Filtmall-Shopping-Skill">skills.sh</a>
</p>
