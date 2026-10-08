# multi-repo-orchestration 文档地图

## 本仓文档

| 文档 | 一句话职责 | 更新触发 |
|---|---|---|
| [README.md](README.md) | 合并版首页：方法论入口 + 五仓架构图/职责表/调度逻辑/任务路由/跨仓纪律/五层总览 | 体系级变更 |
| [docs/SKILL.md](docs/SKILL.md) | 多仓库编排方法论全文（原技能正文：意图与驱动分离/产物驱动/总控落位/任务路由/跨仓纪律/落地步骤） | 方法论更新时 |
| [docs/五层现状总表.md](docs/五层现状总表.md) | 逐仓现状：文档成熟度/当前状态/关键指针 | 各仓 CHANGELOG 变化时 |
| [AGENTS.md](AGENTS.md) | 代理在此仓怎么干活（定位/边界/规则） | 规则变化时 |
| [CHANGELOG.md](CHANGELOG.md) | 本仓变更记录 | 每次提交 |
| [DOCUMENTATION_MAP.md](DOCUMENTATION_MAP.md) | 本文件：文档地图 | 每次提交 |

## 五仓文档权威指针（只指不搬，细节以各仓为准）

| 层 | 仓 | 权威入口 |
|---|---|---|
| ① 采集底座 | multiplatform-content-pipeline | `README.md` + `docs/SYSTEM_ARCHITECTURE.md`（薄指针，指向本仓）+ `docs/WORKFLOW.md` + `docs/DOCUMENTATION_MAP.md` |
| ② 调研方法 | research-toolkit | `SKILL.md`（能力登记）+ `references/research-router.md`（调研类型路由）+ `references/channel-directory.md`（渠道目录）+ `references/industry-packs.md`（行业包） |
| ③ 情报雷达 | ai-intel-monitor | `README.md` + `AGENTS.md` + `01_渠道矩阵/` + `02_监控对象/` + `03_监控机制/` + `04_落地工具/` + `场景应用/` + `DOCUMENTATION_MAP.md` |
| ④ 生产执行 | ai-video-studio | `README.md` + `00_项目总纲.md` + `01_结论与产出/` + `02_决策记录/` + `03_进行中的任务/` |
| ⑤ 运营分发 | self-media-ops | `README.md` + `总纲.md`（五仓速查）+ `docs/SYSTEM_STRATEGY.md`（业务方向）+ `docs/project-management/memory/repo-map.md`（协作地图） |
| 治理参考 | accounting-kb | `README.md` + `AGENTS.md`（治理规范）+ `CHANGELOG.md` + `docs/` + `project-management/` |

## 权威源归属规则

- 本仓 README 的"五仓架构/路由/纪律"为**唯一权威源**（合并自原 system-architecture 与 pipeline 仓 SYSTEM_ARCHITECTURE 的降级迁移）；`multiplatform-content-pipeline/docs/SYSTEM_ARCHITECTURE.md` 已降级为薄指针指向本仓。
- 五仓现状以本仓 `docs/五层现状总表.md` 为**唯一权威总表**；各仓内部状态以其自身 TASK_STATUS/CHANGELOG 为准。
