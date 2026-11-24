# Graph Report - gyomu-kanban  (2026-11-24)

## Corpus Check
- Corpus is ~2,497 words - fits in a single context window. You may not need a graph.

## Summary
- 72 nodes · 126 edges · 9 communities (8 shown, 1 thin omitted)
- Extraction: 92% EXTRACTED · 8% INFERRED · 0% AMBIGUOUS · INFERRED: 10 edges (avg confidence: 0.91)
- Token cost: 94,616 input · 0 output

## Community Hubs (Navigation)
- ボード描画とフィルタ
- 今すぐやること・保留
- GAS接続とキャッシュ
- Graphify設定ドキュメント
- タスク追加と保存
- GAS通信と状態更新
- 編集・削除操作
- 保留モーダル
- タスク編集モーダル

## God Nodes (most connected - your core abstractions)
1. `fetchAll()` - 15 edges
2. `openEdit()` - 14 edges
3. `tasks (task state array)` - 10 edges
4. `rTodo()` - 9 edges
5. `gasCall()` - 8 edges
6. `setStat()` - 8 edges
7. `rRemind()` - 8 edges
8. `doSave()` - 8 edges
9. `closeOv()` - 8 edges
10. `rBoard()` - 7 edges

## Surprising Connections (you probably didn't know these)
- `graphify skill (/graphify trigger)` --conceptually_related_to--> `graphify knowledge graph (graphify-out/)`  [INFERRED]
  .claude/CLAUDE.md → CLAUDE.md

## Import Cycles
- None detected.

## Hyperedges (group relationships)
- **GAS CRUD write then refetch flow** — index_dosave, index_docomplete, index_dodelete, index_doresume, index_dopark, index_gascall, index_fetchall [EXTRACTED 1.00]
- **Render pipeline** — index_render, index_rstats, index_rtodo, index_rremind, index_rboard, index_rpark, index_chtml [EXTRACTED 1.00]
- **Deadline and waiting-time urgency computation** — index_duntil, index_wdays, index_dlcls, index_dltag, index_todo_priority [INFERRED 0.85]

## Communities (9 total, 1 thin omitted)

### Community 0 - "ボード描画とフィルタ"
Cohesion: 0.20
Nodes (15): backupCSV(), Kanban board area, downloadCSV(), Filter toolbar (tbar), rBoard(), 回答待ち3日以上 remind panel, render(), rRemind() (+7 more)

### Community 1 - "今すぐやること・保留"
Cohesion: 0.16
Nodes (11): cHTML(), dlCls(), dlTag(), dUntil(), 保留エリア park area, rPark(), rTodo(), SRC_CLS (source-to-tag class map) (+3 more)

### Community 2 - "GAS接続とキャッシュ"
Cohesion: 0.22
Nodes (7): CACHE_KEY localStorage cache, connectGas(), fetchAll(), GAS_KEY localStorage key, Google Apps Script web app backend (gas_v4.gs), Setup wizard (wiz-area), showWizArea()

### Community 3 - "Graphify設定ドキュメント"
Cohesion: 0.25
Nodes (8): graphify skill (/graphify trigger), .claude/skills/graphify/SKILL.md, graphify-out/graph.json, graphify-out/GRAPH_REPORT.md, graphify knowledge graph (graphify-out/), graphify query / path / explain / section commands, graphify update . (AST-only), graphify-out/wiki/index.md

### Community 4 - "タスク追加と保存"
Cohesion: 0.29
Nodes (4): buildSgrid(), doSave(), openAdd(), setSrc()

### Community 5 - "GAS通信と状態更新"
Cohesion: 0.60
Nodes (4): doComplete(), doResume(), gasCall(), setStat()

### Community 6 - "編集・削除操作"
Cohesion: 0.83
Nodes (4): closeOv(), doDelete(), openEdit(), openPkov()

### Community 7 - "保留モーダル"
Cohesion: 0.67
Nodes (4): closePkov(), doPark(), Park modal (#pkov), pkovOut()

## Knowledge Gaps
- **14 isolated node(s):** `.claude/skills/graphify/SKILL.md`, `graphify query / path / explain / section commands`, `graphify-out/wiki/index.md`, `graphify-out/GRAPH_REPORT.md`, `graphify update . (AST-only)` (+9 more)
  These have ≤1 connection - possible missing edges or undocumented components. (Counts symbols only; 26 node(s) total have ≤1 connection when file, concept and rationale nodes are included.)
- **1 thin communities (<3 nodes) omitted from report** — run `graphify query` to explore isolated nodes.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `fetchAll()` connect `GAS接続とキャッシュ` to `ボード描画とフィルタ`, `タスク追加と保存`, `GAS通信と状態更新`, `編集・削除操作`, `保留モーダル`?**
  _High betweenness centrality (0.234) - this node is a cross-community bridge._
- **Are the 2 inferred relationships involving `fetchAll()` (e.g. with `Google Apps Script web app backend (gas_v4.gs)` and `localStorage cache fallback`) actually correct?**
  _`fetchAll()` has 2 INFERRED edges - model-reasoned connections that need verification._
- **What connects `.claude/skills/graphify/SKILL.md`, `graphify query / path / explain / section commands`, `graphify-out/wiki/index.md` to the rest of the system?**
  _14 weakly-connected nodes found - possible documentation gaps or missing edges._
- **Why does `openEdit()` connect `編集・削除操作` to `ボード描画とフィルタ`, `今すぐやること・保留`, `タスク追加と保存`, `GAS通信と状態更新`, `タスク編集モーダル`?**
  _High betweenness centrality (0.230) - this node is a cross-community bridge._
- **Why does `tasks (task state array)` connect `ボード描画とフィルタ` to `今すぐやること・保留`, `GAS接続とキャッシュ`, `編集・削除操作`, `保留モーダル`?**
  _High betweenness centrality (0.163) - this node is a cross-community bridge._