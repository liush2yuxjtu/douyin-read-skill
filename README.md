# douyin-read-skill — read any Douyin video link with your AI agent

> An Agent Skill that opens a Douyin (抖音) video link in a browser and returns its **caption, author, hashtags, engagement counts, chapters and on-screen text**, plus whether the Douyin web session is logged in. Read-only: it never logs in unless you ask.

[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Agent Skills](https://img.shields.io/badge/Agent%20Skills-SKILL.md-orange)](https://agentskills.io)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-skill-d97757)](https://code.claude.com/docs/en/skills)

[English](README.md) · [中文](README_zh.md)

## Skills

| Skill | What it does |
|---|---|
| [`douyin-read`](skills/douyin-read/SKILL.md) | Reads a `douyin.com` / `v.douyin.com` video page: login status, author `@handle` and date, full caption and hashtags, like / comment / collect / share counts, chapter list, readable on-screen text, final URL |
| [`verify-skill`](skills/verify-skill/SKILL.md) | Local checks for this repo (no CI) |

## Install

```bash
npx skills add liush2yuxjtu/douyin-read-skill --skill douyin-read -g -y
```

Claude Code plugin: `/plugin marketplace add liush2yuxjtu/douyin-read-skill` then `/plugin install douyin-read-skill@douyin-read-skill`.

Or copy by hand:

```bash
git clone https://github.com/liush2yuxjtu/douyin-read-skill
mkdir -p ~/.claude/skills && cp -r douyin-read-skill/skills/douyin-read ~/.claude/skills/
```

Needs an agent with a browser (Douyin has no public API).

## Usage

Paste a Douyin link, or ask "读一下这个抖音视频". The agent opens the exact URL, closes a login modal once if it covers the video (never starts a login), and returns a structured brief: login → author/date → caption → engagement → chapters/subtitles → blockers.

## Related

- [douyin-video-skill](https://github.com/liush2yuxjtu/douyin-video-skill): turn Douyin creator videos into Agent Skills (e.g. `viral-topic-picking`, 爆款选题). Use `douyin-read` to fetch a video first.

## Verify

```bash
bash skills/verify-skill/verify.sh
```

## Disclaimer

Unofficial; not affiliated with Douyin or ByteDance. Respect Douyin's terms and creators' copyright when using what you read.

## License

[MIT](LICENSE)
