# USDD 获取入口 — UI 改动需求文档

**需求背景**：用户在理财页看到 USDD 5% APY 产品时，因为没有 USDD 而不知道如何获取，导致转化流失。在尽量不影响现有布局和主流程的前提下，新增两个固定可见的获取入口。

**涉及页面**：理财首页（市场 Tab）、存入 USDD 页

**原型图预览**：  
**原型/交互图查看：**  
- [GitHub 项目文档仓库](https://github.com/rageencui/tronlink-app-PRD)
- [最新原型图预览（GitHub Page）](https://rageencui.github.io/tronlink-app-PRD/TronLink%20%E7%90%86%E8%B4%A2/tronlink-usdd-wireframe-v6.html)

> 说明：原型图为交互设计初稿，仅供产品&开发参考，具体样式、细节以 UI 最终输出为准。


---

## 改动一：理财首页 · USDD 行

**位置**：市场 Tab → 理财推荐列表 → USDD 行

**改动描述**：在 USDD 行右侧 APY 数字下方新增一行「如何获取 ›」小字链接。

### 详细规格

| 属性 | 值 |
|------|-----|
| 文字内容 | `如何获取 ›` |
| 位置 | APY 数字正下方 |

// 其他样式相关需求（字号、颜色、样式、行高等）由 UI 设计按规范处理，产品文档不做具体要求。

### 点击行为

- **点击「如何获取 ›」**：弹出底部 ActionSheet（或跳转获取引导页），展示两个选项：
  1. **USDT 兑换（PSM）** — 跳转 `https://app.usdd.io/tron/psm`｜ 内部 DApp 浏览器打开 |
  2. **存 TRX 铸造（Vault）** — 跳转 `https://app.usdd.io/tron`｜ 内部 DApp 浏览器打开 |
- **点击行其他区域**：保持原有行为，进入存入 USDD 页面，不变

### 显示条件

- <span style="color: red;">固定显示，不区分用户是否持有 USDD</span>
- 仅 USDD 这一行显示，其他通证行不添加

---

## 改动二：存入 USDD 页

**位置**：存入 USDD 页 → 参与账户表单卡片内部

**改动描述**：在表单 card 内新增两个入口：
① 「可用」行右侧新增「如何获取 ›」内联小字链接；
② 「已参与」数据行下方通过虚线分割，新增固定可见的获取按钮行。

### 入口① 规格：「可用」行右侧小字链接

| 属性 | 值 |
|------|-----|
| 文字内容 | `如何获取 ›` |

**点击行为**：与「改动一」相同——弹出底部 ActionSheet，展示两个选项：
1. **USDT 兑换（PSM）** → 跳转 `https://app.usdd.io/tron/psm`（in-app WebView）
2. **存 TRX 铸造（Vault）** → 跳转 `https://app.usdd.io/tron`（in-app WebView）

**显示条件**：<span style="color: red;">固定显示，不区分余额是否为 0</span>

---

### 入口② 规格：虚线分割 + 获取按钮行

**点击行为**：

| 元素 | 行为 |
|------|------|
| 「USDT 兑换 (PSM)」按钮 | 跳转 `https://app.usdd.io/tron/psm`｜ 内部 DApp 浏览器打开 |
| 「存 TRX 铸造」按钮 | 跳转 `https://app.usdd.io/tron`｜ 内部 DApp 浏览器打开 |

### 显示条件

- <span style="color: red;">两个入口仅当余额为 0 时显示</span>
- 不影响上方输入框、可用余额、已参与数据，以及下方预计日收益、授权按钮等所有原有元素

---

## 跳转链接汇总

| 入口 | 目标 URL | 打开方式 |
|------|----------|---------|
| PSM 兑换 | `https://app.usdd.io/tron/psm` | 内部 DApp 浏览器打开 |
| Vault 铸造 | `https://app.usdd.io/tron` | 内部 DApp 浏览器打开 |
