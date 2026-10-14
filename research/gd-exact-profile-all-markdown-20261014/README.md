# 完整研究资料包

本包生成于 2026-10-14T22:30:02.545213+08:00，用于把同一研究问题交给新的系统测试。

## 直接怎么用

1. 让新系统读取 ALL_RESEARCH_FULL.md，或上传本压缩包供其解压。
2. 把 PROMPT.md 的全文作为你的任务指令发送。PROMPT.txt 内容相同，方便直接复制。
3. 如果系统不能一次读取总文件，按 SOURCE_INDEX.csv 查找 originals/ 中的完整单文件，或按 PARTS_INDEX.csv 读取 parts/。分卷不是摘要，按顺序连接可恢复总文件的每个字节。

## 本包包括什么

- ALL_RESEARCH_FULL.md：3,407 份历史 Markdown 条目全部正文；重复副本和旧版本也逐份保留。
- originals/：每份来源的原始字节副本，文件名为 DOC 编号；来源路径映射在索引中。
- 附加正文：完整公共共享 JSONL 记录和以前网页交接的 TXT 文件，共 15 份独立正文。仅附加非 Markdown 记录的完全重复快照合并了别名，见 MANIFEST.json。
- parts/：155 份 UTF-8 无删减分卷，可按顺序还原总文件。
- literature/：5 份现有主要论文 PDF。
- SOURCE_INDEX.csv、PARTS_INDEX.csv、MANIFEST.json、VALIDATION.json：覆盖范围、定位和完整性核对。

## 明确的收集范围

- project：D:\Danus\runtime\projects\gd-exact-profile-20260926
- intake：D:\Danus\runtime\imports\gd-exact-profile-20260926
- handoff_20261010：D:\Danus\runtime\handoffs\gd-exact-profile-20261010
- webpro_20261010：D:\Danus\runtime\handoffs\gd-exact-profile-webpro-20261010
- archive_core_20261010：D:\Danus\runtime\handoffs\gd-exact-profile-20261010-core.zip 内的全部 Markdown 条目。
- archive_full_20261010：D:\Danus\runtime\handoffs\gd-exact-profile-20261010-full-evidence.zip 内的全部 Markdown 条目。

该范围与此前研究交接的公开资料范围一致。未读取或收录 worker 私有记忆、认证配置、其他项目、Danus 程序本身的文档。不是对整台电脑所有 .md 的扫描。范围内不按质量、有用性、是否重复或是否失败进行筛选。

## 完整性与数学状态

总文件只统一文本编码和换行，没有删减、改写、去重或修正来源正文。原始文件完整字节另存，以便核对。历史 Markdown 中的旧链接、旧指令和原有排版问题保留；阅读时以新提示词、来源日期和证据等级为准。

本次执行的是文件合并和校验，不重新证明数学、不调用新研究模型、不提交 verify。原问题仍按保存资料记为 OPEN。不要把压缩包完整性检查当成数学正确性证明。
