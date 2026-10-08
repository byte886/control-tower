# 体系总控（control-tower）

> **文档类型**：Constitution（体系总控 + 方法论）
> **定位**：**本仓 = 多仓库编排方法论 + 五仓体系实例的唯一权威源**。合并自两个来源：原技能 `multi-repo-orchestration`（方法论全文，见 [docs/SKILL.md](docs/SKILL.md)）+ 原总控仓 `system-architecture`（五仓实例总览，见本 README 与 [docs/五层现状总表.md](docs/五层现状总表.md)）。架构文档不再散落多处，防双写漂移。
> **维护者**：人拍板，AI 执行
> **更新频率**：体系级变更（新增/合并/移除仓库、路由或纪律变化、方法论更新）时

---

## 一、方法论入口（怎么编排多仓体系）

> 完整方法论正文见 **[docs/SKILL.md](docs/SKILL.md)**（原技能全文，87 行）。要点速记：

- **核心原则：意图与驱动分离**——人管方向（意图层，异步不阻塞），系统自治（驱动层，每仓有最小闭环、可独立测试）
- **只通过产物对接，不通过指令对接**——上游产物"就绪"→ 下游即可消费，不等待、不轮询、不发指令
- **总控落位决策表**：有数据源头仓→驱动层文档放底座仓；平级多仓→独立成文；体系庞大（>6 仓）→才考虑独立总控仓
- **落地步骤**：盘仓（按五层归类）→ 定总控 → 建产物对接表 → 写路由表 → 同步指针 → 命名统一 → 分仓推送
- 与 `project-manager`（单仓治理）、`okf-wiki`（知识成品格式）互补：本方法论管**仓与仓之间**的组织

## 二、五仓体系实例总览（本仓库即本实例的总控）

| 层 | 仓库 | 位置 | 回答的问题 | 自治驱动点 |
|---|---|---|---|---|
| ① 采集底座 | **content-pipeline** | `~/Desktop/content-pipeline` | 知识从哪来 | ✅ 数据引擎：给渠道/博主即采集→转写→知识成品 |
| ② 调研方法 | **research-toolkit** | `~/Doubao/skills/research-toolkit`（git 子模块） | 外部信息怎么查 | ✅ 方法层：行业包/渠道目录/分层路由 |
| ③ 情报雷达 | **trend-radar** | `~/Desktop/trend-radar` | 正在发生什么 | ✅ 定时扫描：主题→情报速递（周/双周/月） |
| ④ 生产执行 | **video-studio** | `~/Desktop/video-studio` | 怎么做 | ✅ 接单即产：产品图→成片→门禁 G1-G5 |
| ⑤ 运营分发 | **we-media-ops** | `~/Desktop/we-media-ops` | 怎么卖（方向） | 🔶 人驱动：定方向/选题/优先级（不阻塞下游） |
| 治理参考 | **accounting-kb** | `~/Desktop/accounting-kb` | 怎么治理/怎么写文档 | 治理方法论参考：README/AGENTS/docs 分层、Diátaxis、质量保证 |

## 三、调度逻辑（产物驱动对接表）

> **核心原则：只通过产物对接，不通过指令对接。** 上游产出了什么，下游直接用，不用等谁发话。

| 仓 | 输入（可独立造） | 自测输出 | 下游消费方 |
|---|---|---|---|
| pipeline | 一个渠道/博主（如宝石学家老许） | 知识成品 md（05_knowledge） | sop 取素材、monitor 取情报线索 |
| monitor | 一个主题（如翡翠公盘） | 情报速递 md（01_渠道矩阵→场景应用） | ops 选题、sop 决策 |
| sop | 一张产品图 | 成片/方案图（视频/图） | ops 发布 |
| ops | 一个选题 | 文案+排期 | 对外发布（无下游） |
| toolkit | 一个行业（如鉴藏/翡翠） | 行业包（词库/模板/渠道） | pipeline 采集配置、monitor 矩阵 |

## 四、任务路由表（接到任务先判断）

```
接到任务 → 判断任务类型：
├─ 业务意图（发什么/卖什么/定方向）→ we-media-ops 策略层（docs/SYSTEM_STRATEGY.md）
├─ 采集/知识生成（采某博主/某渠道内容）→ pipeline（docs/WORKFLOW 四阶段）
├─ 查外部资料/选工具/行业调研 → research-toolkit（references/research-router 分层路由 L1-L3）
├─ 盯动态/定时扫描 → trend-radar（周/双周/月机制）
├─ 出图/出视频 → video-studio（SOP + 门禁 G1-G5）
├─ 发朋友圈/自媒体内容 → we-media-ops（写作SOP + AI味检查）
└─ 跨层任务 → 先读本仓 README 路由，再进对应仓；拿不准就高走：先读策略层
```

## 五、跨仓纪律（所有仓遵守）

1. **来源四档强制**：✅已查证（官方一手可回源）/ 🔶经搜索补充（≥2独立源）/ 🟡一方说法 / ⚪未经核实单列——不编造 URL/价格/数据
2. **OKF 统一**：知识成品用 OKF v0.2 标准档 frontmatter（各仓 AGENTS 有 type 词表与校验纪律）；存量不强制回填、新写自然采用
3. **鉴藏总域**：行业/知识归属一律按 `domains/heritage/` 子域表（01_jewelry / 02_jadeite / 03_antiques / 04_furniture / 05_eastern-heritage / 06_western-heritage）
4. **建包顺序**：新子域启用 = 调研技能行业包（词库+模板）→ 监控仓渠道矩阵 → pipeline 采集配置
5. **子模块纪律**：技能类仓库（research-toolkit）改后必须回父仓库 `~/Doubao/skills` 更新指针再 push
6. **定时更新**：周热搜 / 双周工具价格 / 月度渠道规则 / 事件驱动（搜索算法变化、工具上下线）

## 六、五层现状总览

> 各层治理成熟度与当前状态详见 [docs/五层现状总表.md](docs/五层现状总表.md)（逐仓：文档成熟度 / 当前状态 / 关键指针）。总表随各仓 CHANGELOG 更新。

| 层 | 仓 | 治理文件 | 当前状态（2026-10-08 核对） |
|---|---|---|---|
| ① 采集底座 | content-pipeline | AGENTS/README/docs 齐，根 CHANGELOG 已补 | 🔄 采集/知识提取进行中 |
| ② 调研方法 | research-toolkit | SKILL.md + references 16 篇（技能仓口径自洽） | ✅ 能力成型，10 行业包全正式 |
| ③ 情报雷达 | trend-radar | 五台账齐 | ✅ 13/15 里程碑，人工验证期 |
| ④ 生产执行 | video-studio | AGENTS/根 CHANGELOG/PROFILE/编号目录 | 🟢 On Track，M4 待做 |
| ⑤ 运营分发 | we-media-ops | 治理三件套已补全（TASK_STATUS/ISSUES/CHANGELOG） | 🆕 珠宝冷启动第 1 周 |
| 治理参考 | accounting-kb | 治理标杆，全范式齐备（22 ADR） | ⏸ 等人工闸口/风控解除 |

## 相关文档

- 方法论全文：`docs/SKILL.md`（原 multi-repo-orchestration 技能正文）
- 逐仓现状：`docs/五层现状总表.md`
- 详细路由机制（体系级运行规则）：`content-pipeline/docs/SYSTEM_ARCHITECTURE.md`（薄指针，指向本仓）
- 业务方向与选题策略：`we-media-ops/docs/SYSTEM_STRATEGY.md`
- 运营总纲（五仓速查）：`we-media-ops/总纲.md`
- 跨仓库协作地图：`we-media-ops/docs/project-management/memory/repo-map.md`
- 本仓文档地图：`DOCUMENTATION_MAP.md` ｜ 变更记录：`CHANGELOG.md` ｜ 代理规范：`AGENTS.md`
