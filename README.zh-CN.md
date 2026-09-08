[English project overview](README.md)

# DIKWP-PULSE v1.0.0 交付说明 / Delivery Guide

Created by Yucong Duan (段玉聪).

## 1. 系统定位

DIKWP-PULSE（Public Universal LLM Semantic Evaluation）是一个面向当下大模型竞争的开放语义竞技场与可验证贡献网络。它把两类通常分离的任务放进同一可回放系统：

1. 让 Mock、Recorded、Ollama 和 OpenAI-compatible 模型在同一挑战载体上运行；
2. 将代码、模型适配器、挑战、运行、评审、翻译、算力、部署、研究、传播、安全和分诊等十二类贡献分别登记为哈希链收据。

系统完整嵌入 DIKWP-MESH8.1 运行时。D/I/K/W/P 仅由具名责任主体显式给出；未给出的位置保持开放。系统不生成模型总排行榜，不给贡献者排名，不发行积分或代币，也不执行任意 Shell 或自动外部行动。

## 2. 为什么更有机会吸引 GitHub 参与

PULSE不是再增加一个只能下载的成果包，而是提供统一首屏、社交预览、一分钟离线 Demo、可接入真实模型的适配器、GitHub Pages 展示、Issue Forms、Discussion 模板、PR 模板、CITATION、贡献指南和首批可认领任务。其目标是缩短：

`发现项目 -> 运行结果 -> 提交小贡献 -> 获得可验证署名 -> 形成可分享对象 -> 引入下一位参与者`

任何开源项目都不能保证星标或流量；本系统解决的是参与转化机制，而不是虚构关注度结果。

## 3. 一分钟运行

```bash
unzip DIKWP_PULSE_v1.0.0_开放大模型语义竞技场与可验证贡献网络.zip
cd DIKWP-PULSE-v1.0.0
python -m pip install -e .
dikwp-pulse demo --out-dir outputs/demo
```

随后使用浏览器打开：

```text
outputs/demo/index.html
```

无需安装即可运行单文件版本：

```bash
python dist/DIKWP_PULSE.pyz core
python dist/DIKWP_PULSE.pyz conformance --out validation/PYZ_RECHECK.json
python dist/DIKWP_PULSE.pyz demo --out-dir outputs/pyz-demo
```

## 4. 接入真实模型

Ollama：

```bash
dikwp-pulse run \
  --challenge examples/challenges/purpose-preserving-handoff.json \
  --adapter ollama --model qwen3:8b \
  --out outputs/qwen3.run.json
```

OpenAI-compatible：

```bash
export OPENAI_API_KEY='仅在本地环境设置，不得提交到仓库'
dikwp-pulse run \
  --challenge examples/challenges/purpose-preserving-handoff.json \
  --adapter openai-compatible \
  --base-url https://your-endpoint.example/v1 \
  --model your-model \
  --out outputs/model.run.json
```

## 5. 十二类可汇集能量

- code：修复 Issue、增加测试或实现功能；
- adapter：接入新的模型或推理端点；
- challenge：提出可复现的公共挑战；
- run：提供带环境和预算声明的模型运行；
- review：提交具名 D/I/K/W/P 评审；
- translation：翻译 README、挑战和结果页面；
- compute：提供复现实验所需算力；
- deployment：提供部署环境与运行经验；
- research：完成理论、机制或数据对比；
- outreach：制作教程、演示、活动和传播材料；
- security：负责任披露边界缺口；
- triage：复现、分类和连接 Issue。

这些贡献互不折算，不存在个人总分、兑换率或贡献者排行榜。

## 6. GitHub 发布建议

建议仓库名：`DIKWP-PULSE`

建议 Topics：

```text
dikwp, mesh81, llm-evaluation, open-source, ai-agents,
semantic-web, benchmark, model-comparison, reproducibility,
contribution-graph
```

正式发布时应：

1. 上传完整源码历史并推送 `v1.0.0` 注释标签；
2. 将 `assets/social-preview.png` 设置为 Social preview；
3. 开启 Issues、Discussions 和 GitHub Pages；
4. 发布 `release/GITHUB_RELEASE_CN_EN.md` 中的双语 Release；
5. 首先开放仓库内预置的模型适配器、Purpose挑战、三模型复现、双语评审、安全审计和教程任务；
6. 使用段玉聪本人认证账号完成签名、Zenodo DOI 和 ResearchGate 记录。

当前交付没有把尚未发生的仓库 URL、星标、Fork、DOI 或第三方时间戳写成既成事实。

## 7. 原创保护与来源链

原创命名空间：

```text
urn:dikwp:pulse:yucong-duan:2026:v1
```

冻结贡献：`PULSE-C1` 至 `PULSE-C8`。

已经包含：逐文件 SHA-256、Python AST 指纹、规范化 JSON 指纹、有序 Merkle 根、CITATION.cff、NOTICE、CodeMeta、SPDX SBOM、Git 完整历史、注释标签和可恢复 Git Bundle。开源无法绝对阻止复制或改名；这些机制用于重建来源、发现结构同源、核验版本时间线并提高错误归属成本。

## 8. 验证摘要

- Python 单元测试：13/13；
- 源码一致性：20/20；
- Wheel 一致性：20/20；
- 单文件 PYZ 一致性：20/20；
- JSON Schema：5/5；
- 完整显式评审：`11111` 且双向闭合；
- 缺失语义位置：保持开放，不自动补写；
- 贡献账本：正常链可验证，篡改可检测；
- 核心报告：13页；
- Word可访问性：高0、中0、低0；
- PDF预检：可打开、未加密、非扫描、无警告；
- Git：`main`、`v1.0.0`、完整历史 Bundle，`git fsck` 和 `git bundle verify` 均通过。

---

## English summary

DIKWP-PULSE is an open LLM semantic arena and a verifiable contribution network. It runs model-agnostic challenges and records twelve independent forms of community contribution without collapsing models into one leaderboard or contributors into one score. Human reviewers explicitly provide D/I/K/W/P; missing positions remain open. The release contains source code, Wheel, standalone PYZ, offline Pages-ready demo, GitHub community templates, a core report, provenance manifests, an SPDX SBOM, a tagged Git history, and a complete Git Bundle.
