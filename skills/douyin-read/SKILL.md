---
name: douyin-read
description: >-
  Use when the user pastes a Douyin (douyin.com / v.douyin.com) video link or
  asks to read a Douyin video's caption, subtitles, chapters, author, or
  engagement counts, or asks whether the Douyin web session is logged in.
---

# douyin-read

Read a Douyin web video page: login status, author, caption, hashtags,
engagement counts, chapter list, and readable on-screen text.

## Constraints

- Douyin has no API connector: use a browser (agent browser / desktop agent).
- Do not log in unless the user explicitly asks. Never pretend a QR was scanned.
- Open the exact URL the user gave (keep `modal_id` / video id).
- Reply in the user's language; keep handles, hashtags and URLs as shown.
- Never invent text that was not on the page.
- If blocked, deliver what was already captured instead of retrying forever.

## Steps

1. Acknowledge in one line that you are opening the link.
2. Open the exact URL in the browser.
3. Login status: logged in (nickname / avatar visible) or not
   (`Login` / `登录` button, QR or phone login modal).
4. If a login modal covers the video, close it once (close button, Esc,
   `我知道了`) and keep reading. Do not start a login.
5. Extract:
   - page title
   - author `@handle` and publish date
   - full caption (expand `…` / `展开`) and hashtags
   - like / comment / collect / share counts (right-side icons, top to bottom)
   - chapter list (timestamps + summaries) if shown
   - readable on-screen captions or whiteboard text
   - final URL
6. If the tab crashes, report what was captured; reopen in a fresh tab only
   if important fields are still missing.
7. Deliver a structured brief: login -> author/date -> caption ->
   engagement -> chapters/subtitles -> blockers. Add a screenshot when it helps.
8. Offer one useful next step (log in, export notes, read another link).

## Logging in (only when asked)

Use the host's sign-in / user handoff flow for QR or phone OTP, confirm the
nickname afterwards, then re-read the same video URL.

## Success criteria

The user gets the caption and metadata (or a clear blocker) and an honest
logged-in yes/no.