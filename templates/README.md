# 文档模板

模板按 Wiki 的输出类型组织。写入前阅读 [内容约定](../Schema/conventions.md) 和 [工作流程](../Schema/workflows.md)，再按任务选择模板；涉及来源、论断或评测时读取 [质量要求](../Schema/quality.md)。

| 模板 | 用途 | 产物位置 |
| --- | --- | --- |
| [paper](paper/default.md) | 一篇论文的研究问题、方法、结论及证据 | `Wiki/paper/P001_标题.md` |
| [benchmark](benchmark/default.md) | 按论文聚合作者报告的实验配置和结果 | `Wiki/benchmark/B001_标题.md` |
| [topic](topic/default.md) | 围绕研究问题综合多篇论文的判断与分歧 | `Wiki/topic/T001_主题.md` |
| [questions](questions/default.md) | 跟踪需要核实或解决的独立问题 | `Wiki/questions/Q001_问题.md` |
| [Progress](Progress/default.md) | 记录用户计划、实际处理进度与后续工作 | `Wiki/Progress/YYYY-MM-DD.md` |

## 复制与填写

1. 检查 Wiki 索引和已有页面，先确定复用页面还是创建页面；复用已有稳定 ID。
2. 将对应模板复制到产物位置，再填写 YAML 和正文。`{{...}}` 是填写提示，不是事实；发布内容页前删除或替换全部占位和“模板使用说明”。
3. 所有内容页使用相同的 YAML 键：`id`、`type`、`title`、`sources`、`paper_ids`、`topic_ids`、`updated`。列表无项目时保留 `[]`；日期使用 `YYYY-MM-DD`。
4. `sources` 填项目根目录相对路径或 URL 字符串；正文中的 Markdown 本地链接以**生成后的 Wiki 页面**为基准计算相对路径。不要把模板占位文字当成真实链接。
5. 关键结论和数值在正文就近给出来源链接及页码、章节、表格或代码定位。缺少信息时明确写“未报告”“未获得全文”或“无法核验”，按实际情况保留知识缺口。
6. 按工作流程更新关联页面、索引和操作日志，并检查证据与链接。普通问答、只读健康检查不复制模板、不写文件。

## ID 与适用边界

- 论文 `P001`、仓库 `G001`、主题 `T001` 和问题 `Q001` 各自独立编号，数字至少三位。用显式关系表达关联，不根据同号推断关系。
- `B001` 用于 `P001` 的论文评测聚合；`paper_ids` 必须填写该论文 ID。一行只记录一个明确实验配置；非实证论文无需生成 benchmark。
- paper 页的 `paper_ids` 填自身论文 ID；其他内容页填实际关联论文。`topic_ids` 填实际关联主题，topic 页包含自身主题 ID。
- 进度页 ID 为 `PR-YYYY-MM-DD`，同日可更新同一页。只更新 Wiki 中的进度，不改写 Raw 中的用户计划。
- 表格示意行只用于指示填写结构；没有内容时删除示意行并说明原因。模板不提供真实论文结论，也不代表工作已完成。
