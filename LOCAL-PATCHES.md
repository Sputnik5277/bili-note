# 本地修改说明（local 分支）

基于上游 Rimagination/bili-note @ 08fe812（2026-09-22）。维护方式：fetch 上游 → main 快进 → 重放本补丁（`git diff main local` 或 ~/.skills-manager/local-patches/bili-note-no_upper_limit.diff）。

## 修改点
1. `scripts/score_bili_note.py`（3 行）：`no_upper_limit` 标志生效——置位时 upper=0、status 跳过上限判定、输出增加 no_upper_limit 字段
2. `scripts/archive_bili_materials.py`（1 行）：budget 写入 `"no_upper_limit": True`

## 原因
笔记长度不设上限，too_short 结果保留（不因超出推荐字数上限而降级）。
