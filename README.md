# CUADC 成绩计算器 · Score Calculator

[中文](#简介) · [English](#introduction)

---

## 简介

单页 Web 应用，依据《**2026 中国大学生飞行器设计创新大赛竞赛规则**》中「**无人机短距起降**」项目 **第 6.1 条**，估算**单轮**得分 \(S_{\mathrm{turn}}\)。赛项口语中的「**微固**」即本项目（微型固定翼、短距起降与有效载荷计分）。

**本工具仅供备赛估算与方案对比，不构成对竞赛规则的官方解释；最终以大赛发布的规则文本与现场裁判为准。**

### 功能概览

- **参数试算**：有效载荷 \(W_{\mathrm{payload}}\)（g）、空机质量 \(W_{\mathrm{empty}}\)（g）、最大翼展 \(b\)（mm）、起飞距离 \(d\)（m）；同步显示 \(B\)、\(M\)、\(Z\) 与 \(S_{\mathrm{turn}}\)（结果保留两位小数，且不小于 0）。
- **公式展示**：页内使用 KaTeX 渲染规则 6.1 相关公式（含 \(S_{\mathrm{turn}}\)、\(M\)、分段 \(B\)、\(Z\)）。
- **数据可视化**：柱状图对比「当前试算」与成绩库中一、二、三等奖参考柱；起飞距离与 \(B\) 分段标尺。
- **成绩库**：内置 2025 总决赛等参考数据（可检索、自增记录、恢复默认），数据存于本机浏览器。
- **版本快照**：保存多组参数方案，可选**基准快照**查看与当前参数的差异表。
- **界面主题**：浅色 / 深色 / 跟随系统，偏好在 `localStorage` 中保存。

### 技术说明

- 纯静态：**单个 `index.html`**，无构建步骤。
- 依赖 CDN：KaTeX、Google Fonts（Inter / Noto Sans SC / JetBrains Mono）。
- 数据仅存用户浏览器本地（`localStorage`），清除站点数据或换设备会丢失。

### 本地使用

1. 克隆本仓库或下载 `index.html`。
2. 用浏览器直接打开 `index.html`，或通过任意静态文件服务器打开项目目录（便于部分浏览器对 `file://` 的限制）。

示例（已安装 Node.js）：

```bash
npx --yes serve .
```

然后在浏览器中访问终端里提示的本地地址。

### 与规则的关系

- 总成绩取**两轮较高者**（规则 6.2），**本页仅计算单轮** \(S_{\mathrm{turn}}\)。
- 起飞距离 \(d > 2.4\,\mathrm{m}\) 时，规则 6.1 仅列出两档 \(B\)；工具按 \(B=0\) 提示警告，请以现场裁判解释为准。

---

## Introduction

A single-page, static web app that estimates the **single-round** score \(S_{\mathrm{turn}}\) for the **CUADC 2026** ruleset, section **6.1**, event **“UAV short takeoff and landing”** (often called **“微固”** in casual Chinese among teams).

**This tool is for training and design trade-offs only. It is not an official interpretation of the competition rules; the published rules and field officials prevail.**

### Features

- **Inputs**: payload mass, empty mass, wingspan \(b\) (mm), takeoff distance \(d\) (m); shows factors \(B\), \(M\), \(Z\) and \(S_{\mathrm{turn}}\) (two decimal places, floored at 0).
- **Typeset math** via KaTeX (formulas aligned with rule 6.1).
- **Charts**: bar comparison against reference tiers; takeoff distance ribbon for the \(B\) tiers.
- **Reference library**: embedded finals data (searchable, editable locally, resettable); stored in the browser.
- **Snapshots**: save/compare parameter sets against a selected baseline.
- **Theme**: light / dark / system, persisted locally.

### Tech stack

- One file: `index.html` (no bundler).
- CDN: KaTeX, Google Fonts.

### Local use

Open `index.html` in a browser, or serve the folder with any static server (see command above).

### Rules note

- **Overall** score uses the **better of two rounds** (rule 6.2); **this page computes one round only**.
- For \(d > 2.4\,\mathrm{m}\), rule 6.1 only tabulates two \(B\) bands; the tool sets \(B = 0\) with a warning—follow the officials on site.

---

## Repository

GitHub: [stianyu798-arch/CUADC-Score-Cauculator](https://github.com/stianyu798-arch/CUADC-Score-Cauculator)
