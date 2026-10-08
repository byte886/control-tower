# multi-repo-orchestration 变更记录

> 只记体系级变更（新增/合并/移除仓库、路由、纪律、治理标准、方法论变化）；各仓细节变更记在各仓自己的 CHANGELOG。

## 2026-10-08（合并）

- ［合并］**multi-repo-orchestration 技能与 system-architecture 总控仓合并为单一桌面仓**（用户拍板）：技能方法论全文入 `docs/SKILL.md`，原总控仓五仓总览/现状表/治理文档保留于本仓；README 重写为合并版（方法论入口 + 五仓现状 + 指针表）
- ［定位］本仓 = 多仓库编排方法论 + 五仓体系实例的**唯一权威源**；原 `system-architecture` 名称废弃（GitHub 远端删除），原技能远端 `byte886/multi-repo-orchestration` 由桌面仓接管
- ［变更］技能目录 `~/Doubao/skills/multi-repo-orchestration/SKILL.md` 降级为薄指针（保留 frontmatter 使豆包技能可发现，完整方法论指向本仓 `docs/SKILL.md`）
- ［收敛］全仓 README 指针从 system-architecture 更新为 multi-repo-orchestration（multiplatform-content-pipeline / web-research-toolkit / ai-intel-monitor / heritage-ai-video-sop / self-media-ops / accounting-kb）

## 2026-10-08（建仓·原 system-architecture）

- ［建仓］创建五仓体系总控仓 system-architecture（本记录保留历史；该仓名与远端 2026-10-08 随合并废弃）
- ［新增］README：五仓架构图 + 职责表 + 调度逻辑（产物驱动对接）+ 任务路由表 + 跨仓纪律 + 五层现状总览
- ［新增］docs/五层现状总表.md：逐仓治理成熟度/当前状态/关键指针（首次核对）
- ［新增］AGENTS.md：代理工作规则（总控仓定位/边界/操作规则/OKF/commit 规范）
- ［新增］DOCUMENTATION_MAP.md：本仓文档地图 + 五仓文档指针
- ［收敛］各仓 README 加"总控仓指针"一行：multiplatform-content-pipeline / web-research-toolkit / ai-intel-monitor / heritage-ai-video-sop / self-media-ops / accounting-kb（只加指针，不改既有内容）
