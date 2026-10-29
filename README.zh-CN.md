# GrokBot-LeanOps（中文）

**面向 Grok Bot 的低冗余执行方案：减少无用步骤、明确授权边界、用真实任务测量效率。**

> 社区独立项目，非 xAI 官方项目。不宣称“必省 50% Token”或其他未经实测的数据。具体功能以你的账号和最新[官方文档](https://docs.x.ai/grok-bot/skills-routines-and-automations)为准。

## 使用方法

1. 复制 [`instructions/LEAN_GLOBAL.md`](instructions/LEAN_GLOBAL.md) 中的总控指令，先放到**一个测试 Bot**，不要批量覆盖所有 Bot。
2. 先让 Bot **只读盘点**现有 Routine、常见重复动作和最近一次任务的过程，不要自动修改配置。
3. 需要执行具体任务时，参考 [`skills/lean-execution/SKILL.md`](skills/lean-execution/SKILL.md)。官方支持的情况下由 Grok Bot 将其适配、保存为私有 Skill；不要假设复制 GitHub 文件会自动安装。
4. 对照测试 5 组难度接近的任务，在 [`examples/usage-log.csv`](examples/usage-log.csv) 记录真实使用量、成功率、返工时间。
5. 验证有效后，再逐步启用低频 Routine 或多个 Bot。

## 核心规则

- **先复用**已审核成果，有时效要求的资料必须更新。
- 结构化重复操作优先尝试**有授权的 API/CLI**，必要时才模拟浏览器点击。
- **不要反复读整段长对话**；以简短阶段摘要传递任务。
- Skill **按需加载**，避免将全部规则塞入常驻指令。
- 定时任务按需触发，避免无意义轮询；无变化不代表无额度成本。
- **对外发送、网站发布、购买、删除和生产环境修改**应通过明确授权。
- Prompts 无法强制执行额度限额或真正隔离不同 Bot；需要平台能力与程序控制。

项目文件说明与英文 README 相同。原创内容采用 [MIT License](LICENSE)，引用第三方项目仅提供链接，不打包他人的源代码或 Skill。
