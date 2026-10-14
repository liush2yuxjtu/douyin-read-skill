# douyin-read-skill

Agent skill: open a Douyin (抖音) video link in a browser and read its caption,
author, engagement counts, chapters and on-screen text, plus report whether the
Douyin web session is logged in. Read-only: never logs in unless asked.

## Install

```bash
npx skills add liush2yuxjtu/douyin-read-skill --skill douyin-read -g -y
```

Or copy `skills/douyin-read/SKILL.md` into your agent's skills folder.

## Trigger

Paste a `douyin.com` / `v.douyin.com` link, or ask "读一下这个抖音视频".