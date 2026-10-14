# douyin-read-skill — 让 AI agent 读懂抖音视频链接

> 一个 Agent Skill：在浏览器里打开抖音视频链接，返回**文案、作者、话题标签、点赞/评论/收藏/分享数、章节和画面文字**，并告诉你抖音网页端是否已登录。只读：除非你要求，绝不登录。

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Agent Skills](https://img.shields.io/badge/Agent%20Skills-SKILL.md-orange)](https://agentskills.io)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-skill-d97757)](https://code.claude.com/docs/en/skills)

[English](README.md) · [中文](README_zh.md)

## Skills

| Skill | 作用 |
|---|---|
| [`douyin-read`](skills/douyin-read/SKILL.md) | 读取 `douyin.com` / `v.douyin.com` 视频页：登录状态、作者 `@昵称` 与发布日期、完整文案和话题、点赞/评论/收藏/分享数、章节列表、画面可读文字、最终链接 |
| [`verify-skill`](skills/verify-skill/SKILL.md) | 本仓库的本地校验（不使用 CI） |

## 安装

```bash
npx skills add liush2yuxjtu/douyin-read-skill --skill douyin-read -g -y
```

Claude Code 插件：`/plugin marketplace add liush2yuxjtu/douyin-read-skill`，再 `/plugin install douyin-read-skill@douyin-read-skill`。

或手动复制：

```bash
git clone https://github.com/liush2yuxjtu/douyin-read-skill
mkdir -p ~/.claude/skills && cp -r douyin-read-skill/skills/douyin-read ~/.claude/skills/
```

需要带浏览器能力的 agent（抖音没有公开 API）。

## 使用

粘贴抖音链接，或者说"读一下这个抖音视频"。agent 会打开原链接；若登录弹窗挡住视频，只关闭一次（不会发起登录），然后按"登录状态 → 作者/日期 → 文案 → 互动数据 → 章节/字幕 → 阻碍"输出结构化摘要。

## 相关项目

- [douyin-video-skill](https://github.com/liush2yuxjtu/douyin-video-skill)：把抖音博主视频做成 Agent Skill（如 `viral-topic-picking` 爆款选题），可先用 `douyin-read` 读取视频。

## 校验

```bash
bash skills/verify-skill/verify.sh
```

## 声明

非官方项目，与抖音、字节跳动无关。使用读取到的内容时请遵守抖音条款并尊重创作者版权。

## 许可证

[MIT](LICENSE)
