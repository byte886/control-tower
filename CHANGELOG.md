# control-tower 变更记录

> 只记体系级变更（新增/合并/移除仓库、路由、纪律、治理标准、方法论变化）；各仓细节变更记在各仓自己的 CHANGELOG。

## 2026-10-12（维护·五层现状总表刷新）

- ［评审］docs/2026-10-12-independent-governance-review.md：旁观者独立评审入库（复核 commit 3bd59d9 七条 P1 全部闭环 + 查漏）。
- ［修正］C-1 五层现状总表③trend-radar 关键指针：删去虚构的"control-tower 反向指针"，改为"尚未落地（实测全仓零引用），待补"，对齐 AGENTS 规则2"事实以读取为准"。
- ［修正］C-2 AGENTS.md 补"冷启动必读（路由）"段：指向 DOCUMENTATION_MAP 入口 + 治理标杆（accounting-kb 分层样板、content-pipeline DOCUMENTATION_PRINCIPLES/ADR-001）。
- ［修正］C-3 docs/SKILL.md frontmatter 补 `type: Methodology`（okf E2 修复）。
- ［补登］research-toolkit 改名同步（见 2026-10-08 节）。
- ［刷新］docs/五层现状总表.md 按 2026-10-12 逐仓核对重刷，销项 7 条 P1：①content-pipeline「缺根 CHANGELOG」改为「根 CHANGELOG 已补（2026-10-08 起建账）」；②`SYSTEM_ARCHITECTURE.md`「事实上的五仓总控/降级待确认」改为「薄指针，已指向本仓 control-tower；v1 全文归档 `content-pipeline/docs/archive/SYSTEM_ARCHITECTURE_v1_full_2026-10-08.md`」；③业务进度「台账停 09-23」改为「10-12 活跃：郭颖 B 级数据管线 commit 4f22a38 + 视频资产台账 manifest 387 条（238 已下载）」；④删除 video-studio「README 第 41 行发现层指针→trend-radar」这一不存在的行号锚点（编号目录六槽位自导航）；⑤旧名 `ai-video-studio` 改为「改名 video-studio（10-06 曾用名，10-09 定现名）」；⑥we-media-ops「缺 TASK_STATUS/ISSUES/CHANGELOG」改为「活态台账已补齐（根目录三件套在）」；⑦两仓 AGENTS 反向指针 control-tower 已落地（2026-10-12），总表已注明。
- ［清理］五层现状总表「建仓后遗留待办」销项 #1（SYSTEM_ARCHITECTURE 降级）、#3（pipeline 根 CHANGELOG）、we-media-ops 台账补课条目，仅保留 we-media-ops README 目录树对齐 + LICENSE、父仓 ~/Doubao git 卫生、六件套基线三项。
- ［同步］③ trend-radar 与 ⑤ we-media-ops 关键指针中残留的"→ pipeline SYSTEM_ARCHITECTURE（机制层/被指为唯一权威）"两处，同步改为"→ control-tower（机制层）"，与 P1-2 降级后权威归属一致。
- ［刷新］README.md 五层现状表头快照日期 2026-10-08 → 2026-10-12。
- ［补全］AGENTS.md OKF 校验命令由裸名 `okf_validate.py` 补全为 `~/Doubao/skills/okf-wiki/scripts/okf_validate.py`。

## 2026-10-09（改名）

- ［改名］采集底座仓 `multiplatform-content-pipeline` → **`content-pipeline`**（用户拍板：原名过长；content-pipeline 为英文标准术语，砍掉 multiplatform 隐含属性，与体系 2 词风格统一）。本地目录 `~/Desktop/content-pipeline`、GitHub 远端 `byte886/content-pipeline` 同步；本仓 README/docs/SKILL/DOCUMENTATION_MAP/五层现状总表指针同步更新；we-media-ops 子模块 URL 同步。
- ［改名］总控仓 `multi-repo-orchestration` → **`control-tower`**（用户拍板：control-tower 为 Gartner 供应链控制塔术语，语义=对整个体系的统一可见+决策，与"总控仓"定位直译一致；此前候选 repo-orchestration 因"编排对象是仓与仓的协作而非 repo 本身"被弃）。本地目录 `~/Desktop/control-tower`、GitHub 远端 `byte886/control-tower` 同步；全仓指针同步更新。
- ［改名］情报雷达仓 `ai-intel-monitor` → **`trend-radar`**（用户拍板：intel 非正式且撞 Intel 品牌；trend-radar 有 TrendRadar 53k stars 先例，语义=追踪趋势变化，与体系去 ai 前缀统一）。本地目录 `~/Desktop/trend-radar`、GitHub 远端 `byte886/trend-radar` 同步。
- ［改名］生产执行仓 `ai-video-studio` → **`video-studio`**（体系去 ai 前缀统一：AI 在体系内不言而喻）。本地目录 `~/Desktop/video-studio`、GitHub 远端 `byte886/video-studio` 同步。

## 2026-10-08（改名）

- ［补登·同步］调研方法技能 `web-research-toolkit` → **`research-toolkit`**（commit 2d103ae/b66178a，2026-10-08 22:53–22:54）：本仓 README/DOCUMENTATION_MAP/docs/SKILL.md/五层现状总表②技能名同步更新；历史曾用名见本节（建仓）收敛清单。
- ［改名］运营分发仓 `self-media-ops` → **`we-media-ops`**（用户拍板：We Media 为"自媒体"英文原生词源，2003 美国新闻学会《We Media》报告；ops = Operations 标准缩写非中译英）。本地目录 `~/Desktop/we-media-ops`、GitHub 远端 `byte886/we-media-ops` 同步；本仓 README/docs/SKILL/DOCUMENTATION_MAP/五层现状总表指针同步更新。

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
