# step_silver

预定非负步长梯度下降的 Zhang–Jiang 精确常数/曲线 minimax 问题：完整研究资料与新系统测试提示词。

**原始数学问题仍未解决。** 本仓库用于资料交接和继续研究，旧系统接受事实、未验证草稿、数值观察和中断线索均需保留各自的证据等级。

## 最新进度：2026-10-17，研究已暂停

本次保存了 R15–R17 的全部新增研究 Markdown、轮次记录和原始候选稿。Goal 已按用户要求暂停；历史文件中的 ACTIVE 状态不代表允许重新启动研究。

- [最新进展与恢复入口](research/gd-exact-profile-progress-20261017/README.md)
- [R17 阶段总结与尚未闭合的缺口](research/gd-exact-profile-progress-20261017/research/resume_20261017_r17/R17_PROGRESS.md)
- [增量压缩包，约 239 KB](archives/gd-exact-profile-progress-20261017.zip?raw=true)
- [文件来源与哈希清单](research/gd-exact-profile-progress-20261017/MANIFEST.json)

新增结果包括任意深度的受限混合轨迹结论、精确 Silver 参数下的全函数类估计，以及候选下界拼接路线的具体代价分析。一般光滑凸函数上的目标证明仍未完成；人工审计通过不等于 Danus 验证器接受。此前完整档案保留在下方，新增内容没有再次拼接成重复的大文件。

## 如何交给新系统

1. 把 [PROMPT.md](PROMPT.md) 全文作为任务消息发送。
2. 同时提供 [最新增量包](archives/gd-exact-profile-progress-20261017.zip?raw=true) 与 [历史完整资料压缩包](archives/gd-exact-profile-all-markdown-20261014.zip?raw=true)，或让具有仓库访问能力的系统先读取最新进展入口。
3. 主文件较大，不能在线预览时可下载原始文件，或按来源索引读取单文件和无删减分卷。不要把未读取的内容当成已经审查。

## 资料入口

| 文件 | 内容 |
|---|---|
| [完整压缩包，约 90 MB](archives/gd-exact-profile-all-markdown-20261014.zip?raw=true) | 已完成校验的完整交接包 |
| [完整总 Markdown，约 80 MB](research/gd-exact-profile-all-markdown-20261014/ALL_RESEARCH_FULL.md) | 3,407 份历史 Markdown 条目全文；重复副本和旧版本均保留 |
| [新系统提示词](PROMPT.md) | 完整问题、成功标准、现有缺口和研究要求；路径已适配本仓库 |
| [包内原始说明](research/gd-exact-profile-all-markdown-20261014/README.md) | 收集范围、使用方法和证据边界 |
| [来源索引](research/gd-exact-profile-all-markdown-20261014/SOURCE_INDEX.csv) | DOC 编号、来源路径、原始哈希、正文位置 |
| [原始逐份副本](research/gd-exact-profile-all-markdown-20261014/originals/) | 保留原始文件字节 |
| [155 份无删减分卷](research/gd-exact-profile-all-markdown-20261014/parts/) | 按顺序连接可逐字节恢复总 Markdown |
| [分卷索引](research/gd-exact-profile-all-markdown-20261014/PARTS_INDEX.csv) | 每卷的顺序、字节位置和涉及的 DOC |
| [主要论文 PDF](research/gd-exact-profile-all-markdown-20261014/literature/) | 5 份现有论文副本 |
| [完整清单](research/gd-exact-profile-all-markdown-20261014/MANIFEST.json) / [校验记录](research/gd-exact-profile-all-markdown-20261014/VALIDATION.json) | 文件覆盖与完整性检查结果 |

## 原始目标

对全部有限维光滑凸函数、全部预定非负步长和原始选择的最小点/起点，保持

    W_n(h) = sup 2(f(x_n)-f_*) / (L ||x_0-x_*||^2),
    W_n^* = inf_(h >= 0) W_n(h),
    U_n^ZJ = 1/B_n.

完整判断

    lim_(n -> infinity) W_n^*/U_n^ZJ = 1

是否成立。精确基准 B_n 保留全部整数切分。肯定答案需要全步长、全充分大步数的统一下界；否定答案需要严格的全函数类渐近分离。仅匹配 Silver 指数、有限步数实验或受限函数族结论均不足。

完整定义在总 Markdown 的 DOC-000001；建议阅读顺序已列在总文件开头。

## 完整性

- 压缩包 SHA-256：d121ea46f86cafe8c4588e8f5942bdcdd07f885aacd347632bb69303442936b5
- 总 Markdown SHA-256：f57197fc2936367ca26e08d81eca8758243aa2c417643c356392b83506df2f8b
- Markdown 条目：3,407；另有 15 份完整共享记录或此前网页交接文本。
- 本次发布的原始资料副本与本地已验证交接包逐文件一致。

仓库中的旧本地路径、旧 prompt、预算及运行指令属于历史资料，不应作为当前系统的操作授权。数据完整性校验不等于数学正确性证明。原文和论文的来源信息保留在各文件中。
