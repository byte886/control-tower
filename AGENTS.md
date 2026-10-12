# AGENTS.md — control-tower 代理工作规则

> 本仓是五仓体系的**总控/方法论仓**（合并自原 system-architecture 总控仓与原 multi-repo-orchestration 技能）：维护多仓库编排方法论 + 体系级总览与指针，不重复维护各仓细节正文。所有跨仓任务先读本仓 README 路由表，再进对应仓；跨仓组织方法疑问读 docs/SKILL.md。

## 冷启动必读（路由）

首次接触本仓或接跨仓任务按序：① 本文件（代理规则）→ ② `README.md`（五仓架构/任务路由表/跨仓纪律，唯一权威源）→ ③ `DOCUMENTATION_MAP.md`（文档地图，定位细节）。**文档写作落位与 README 防则遵循治理标杆，不复制其正文**：accounting-kb（README/AGENTS/docs 分层样板）+ content-pipeline `project-management/standards/DOCUMENTATION_PRINCIPLES.md`（8 类文档词典/新增内容落位决策表/README 防则）+ `decisions/ADR-001`（五原则）。本仓只指不搬。

## 仓定位与边界

- **是什么**：五仓体系（采集/调研/情报/生产/分发 + 治理参考）的唯一权威源总览。收敛散落的架构文档（repo-map.md / 总纲.md / SYSTEM_ARCHITECTURE.md）为一份总表。
- **不是什么**：不是执行仓。不承接具体采集/调研/监控/生产/发布任务（这些按路由表进对应仓）。
- **更新触发**：体系级变更（新增/移除仓库、路由变化、纪律变化、五层现状变化）→ 更新本仓并同步各仓 AGENTS 指针。

## 本仓文件职责

| 文件 | 职责 |
|---|---|
| `README.md` | 总控仓首页：五仓架构图/职责表/调度逻辑（产物对接）/任务路由/跨仓纪律/五层总览 |
| `docs/五层现状总表.md` | 逐仓现状：文档成熟度/当前状态/关键指针（每层一行结论），随各仓 CHANGELOG 更新 |
| `AGENTS.md` | 本文件：代理在此仓怎么干活 |
| `CHANGELOG.md` | 本仓变更记录（体系级变更才记） |
| `DOCUMENTATION_MAP.md` | 本仓文档地图 + 五仓文档指针 |

## 代理操作规则

1. **只通过产物对接，不通过指令对接**：本仓只做总览与指针，不向其他仓下达指令。
2. **事实以读取为准**：涉及各仓状态/文档存在性必须实际读取对应仓文件，不编造、不凭记忆；不确定标"待核实"。
3. **来源四档强制**：✅已查证 / 🔶经搜索补充 / 🟡一方说法 / ⚪未经核实——不编造 URL/价格/数据。
4. **只加指针不改结论**：向各仓 README 加总控仓指针时，只加一行，不动既有内容与结论。
5. **OKF 规范**：本仓长文采用 OKF v0.2 YAML frontmatter（type 词表：Constitution / Reference / Guide / Methodology），提交前跑 `~/Doubao/skills/okf-wiki/scripts/okf_validate.py` 校验。**约定（2026-10-12 评审澄清）**：根 README/AGENTS/CHANGELOG/DOCUMENTATION_MAP 与 blockquote 元数据头的 docs 文档（`> **文档类型**：…`，与 accounting-kb 标杆一致）——标杆仓自身对同类根文件亦报 E1，故 okf E1（缺 YAML frontmatter）对这几份为**预期项、不强制**；校验以"无新增硬错误、SKILL.md 等 YAML 文档 E=0"为准。
6. **commit 规范**：`docs: 一句话变更`（参照 accounting-kb 风格），体系级变更附影响清单。

## 与会计知识库（accounting-kb）的关系

- accounting-kb 是本体系的**治理方法论参考**（README/AGENTS/docs 分层、Diátaxis 文档分类、质量保证清单）。
- 本仓按同一治理标准建仓：README（章程首页）+ AGENTS（代理规则）+ docs（分层正文）+ CHANGELOG + DOCUMENTATION_MAP。

## 修改纪律

- 修改 README 的"五仓架构/路由表/纪律"属**体系级高扩散变更**：先出方案与影响清单，用户确认后同步五仓 AGENTS 指针。
- 五层现状总表更新为低风险变更：随各仓 CHANGELOG 变化直接更新，无需确认。
