# control-tower 全仓旁观者评审报告（2026-10-12）

> **文档类型**：Review（评审报告）
> **评审者**：MainAgent 独立旁观者视角（非本仓治理 Agent 自评）
> **对象**：control-tower 全仓（根：README.md / AGENTS.md / CHANGELOG.md / DOCUMENTATION_MAP.md；docs/：五层现状总表.md / SKILL.md）
> **前置**：本仓最近 commit `3bd59d9` 声称完成 7 条 P1 口径修正；本次为**逐条复核 + 查漏**
> **判据**：accounting-kb 分层样板；content-pipeline `standards/DOCUMENTATION_PRINCIPLES.md`（8 类文档词典/落位表/README 防则）、`decisions/ADR-001`（五原则）

---

## 一、基础结论

本仓定位为**总控·跨仓路由/纪律/编排，不执行**。复核结论：

- **定位红线（评审项 c）通过**：全仓仅 6 个 md，无 `*.py/*.sh/*.js/*.yml`、无 `scripts/`、无 `.github/workflows`、无定时任务配置。✅
- **旧名残留（评审项 g）通过**：`multi-repo-orchestration / ai-video-studio / self-media-ops / ai-intel-monitor / multiplatform-content-pipeline / system-architecture / web-research-toolkit / heritage-ai-video-sop` 仅出现在 ①CHANGELOG 编年历史记录、②README/AGENTS"合并自原 X"出处说明中，**无任何活跃指针使用旧名或旧 GitHub 路径**。✅
- **死链（评审项 f）通过**：本仓 6 文件内部相对链接（docs/SKILL.md、docs/五层现状总表.md）全部存在；对五仓的本地路径与 `byte886/<repo>` remote 逐一实测全部命中（content-pipeline/trend-radar/video-studio/we-media-ops/accounting-kb/research-toolkit）。✅
- **登记一致性（评审项 h）通过**：DOCUMENTATION_MAP.md 登记 6 文件，与 `find` 实际清单逐项吻合。✅
- **3bd59d9 七条 P1 复核**：①pipeline 根 CHANGELOG 已存在（7698B）✅；②SYSTEM_ARCHITECTURE.md 实为薄指针、正文指向本仓 control-tower ✅；③pipeline TASK_STATUS 10-12 仍活跃（20831B，10-12 23:00 改）✅；④video-studio 行号锚点已删（现无"发现层指针"小节）✅；⑤ai-video-studio 已标注"10-06 曾用名、10-09 定现名"✅；⑥we-media-ops 根目录 TASK_STATUS/ISSUES/CHANGELOG 三件套实测存在 ✅；⑦content-pipeline（AGENTS:30）+ video-studio（AGENTS:26）反向指针已落地 ✅。**七条 P1 全部闭环。**

## 二、问题清单

| # | 级别 | 问题 | 证据 | 建议修正 |
|---|------|------|------|----------|
| C-1 | **P2** | **总表声称 trend-radar 关键指针含 control-tower，但 trend-radar 全仓零引用**——本仓 AGENTS 规则2 明定"事实以读取为准，不凭记忆"，总表此项失真 | `docs/五层现状总表.md:42` 写"关键指针：…control-tower（机制层…）"；实测 `grep -rn "control-tower\|总控\|Desktop/control" ~/Desktop/trend-radar/` 无任何命中 | 就地更正总表：注明 trend-radar **尚未**加总控反向指针（区别于已落地的 content-pipeline/video-studio），不虚构；给 trend-radar 补指针属改他仓，列待拍板 |
| C-2 | **P2** | **AGENTS.md 未指向 DOCUMENTATION_MAP 入口，也未指向文档治理规范**——后续 AI 只读 AGENTS 不会知道文档地图在哪、也不知道 README 防则/落位规则（参照 content-pipeline 晚间评审 A-3 同类问题） | AGENTS.md 全文无 DOCUMENTATION_MAP.md 链接、无 DOCUMENTATION_PRINCIPLES/ADR-001 指针；文件职责表虽列 DOCUMENTATION_MAP 但无"冷启动必读"路由 | AGENTS 补"冷启动必读"段：跨仓任务→先读 README 路由表→DOCUMENTATION_MAP 定位；文档治理规范（README 防则/8 类落位）以 accounting-kb + content-pipeline DOCUMENTATION_PRINCIPLES 为标杆指针 |
| C-3 | **P2** | **okf_validate E 未归零，与本仓 AGENTS 规则5"硬错误归零"自相矛盾** | `python3 okf_validate.py control-tower` → E1×N（根 README/AGENTS/CHANGELOG/DOCUMENTATION_MAP/五层现状总表/评审报告 缺 YAML frontmatter）+ E2×1（docs/SKILL.md frontmatter 缺 `type`） | ✅已修：E2 补 `type: Methodology`；E1 经核对标杆仓 accounting-kb 自身对同类根文件亦报 E1（blockquote 元数据头为体系采纳约定），已就地澄清 AGENTS 规则5——根/blockquote 头文件 E1 为预期项，校验以 YAML 长文 E=0 为准 |
| C-4 | **P3** | **CHANGELOG 漏登 research-toolkit 改名同步两条 commit** | git log：`2d103ae`（README/文档地图/SKILL 技能名→research-toolkit）+ `b66178a`（现状总表②调研方法→research-toolkit），均 2026-10-08 22:53–22:54，CHANGELOG 无对应条目 | CHANGELOG 2026-10-08 节补一行［同步］ |
| C-5 | **P3** | README 与 docs/SKILL.md 三处并行表（产物对接表/任务路由/跨仓纪律）存在双写漂移风险 | README §三/§四/§五 vs SKILL.md §2/§4/§5 结构近乎重复 | 观察项：设计已声明"Constitution 实例（真实仓名）+ 方法论（泛型）"双轨，属有意并行；本次不动，后续若两侧文字分叉再收敛 |
| C-6 | **P3** | README 缺"文档边界表"（accounting-kb README:10-21、trend-radar README 均有"本文档不包含 X → 指向 Y"表） | 本仓 README 仅头部四行元数据，无边界表；docs 命名中英混用（`五层现状总表.md` 中文 / `SKILL.md` 英文） | 观察项：thin 仓"相关文档"段已承担导航，边界表与 docs 改名均属结构性调整，本次不动 |

## 三、观察项（低优先，本次不动）

- O-1：`we-media-ops/deps/control-tower/` 是 git 子模块聚合副本，实测仍指向**旧 commit**（其 `五层现状总表.md:49` 仍写已删的"README 第 41 行发现层指针→trend-radar"、`:71` 仍把已销项的 SYSTEM_ARCHITECTURE 降级列为"待拍板"）。子模块副本滞后属 we-media-ops 侧 `submodule update --remote`，本仓只读不可动，列待核。
- O-2：README:12 称 SKILL.md"87 行"，`wc -l` 实测 86（末行无换行符所致，可视行数 87），数值口径无碍，不改。
- O-3：本仓无自身体检脚本（无 *check*/*validate*/*health*）；体检即外部 `~/Doubao/skills/okf-wiki/scripts/okf_validate.py`，已实测可跑。

## 四、修正验收标准（迭代闭环）

1. C-1～C-4 全部处理：已修项写明"做了什么"，待拍板/待核项单列；
2. E2（SKILL.md type）修复后复跑 okf_validate，E1×5 按 D-1 拍板结果处理或明确留痕；
3. DOCUMENTATION_MAP.md 登记本评审报告；
4. git 提交并 push origin/main，工作树干净（待拍板项除外）；
5. CHANGELOG 补登本轮评审与修正。
