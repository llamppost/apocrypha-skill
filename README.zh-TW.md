# 後傳孵化器 · Apocrypha

> [English](README.md) · [中文](README.zh-TW.md)

> Drop in any world — a film, a book, a person, an event, a board game — and Apocrypha hatches a self-consistent, installable, playable text-game GM where **you** step inside and live your own continuation. The engine ships no IP; you bring the world.
>
> 你給它一個世界，它孵化出一段屬於「你」的後傳。它不重述原作，它讓你走進去活一遍。

**Made by [llamppost](https://llamppost.ai) · MIT License**

---

## 這是什麼

Apocrypha 是一台**孵化引擎**：餵它一個世界（一個 IP 或主題），它用一套精簡的世界蒸餾邏輯把世界觀拆透、解出「世界 DNA」，再灌進固定的模擬器骨架，吐出一支**世界自洽、可安裝、可即玩**的沉浸式文字遊戲 GM。

產物的本質是**後傳**：你把自己插進那個世界，孵化一段原作裡沒有、但邏輯上站得住的延續故事。你可以選三種玩法：

- **原創角色自插** — 在那個世界活出一條書裡沒跟到的線
- **扮演正典角色** — 直接成為書中某個角色本人
- **見證正典** — 跟著某個角色的線走，看他會發生什麼

連桌遊都能孵：給它一套社交推理規則，它產出的不是說故事，而是一台會發牌、跑回合、操控 AI 對手、藏住隱藏身份的「遊戲跑分器」。

## IP 姿態（重要）

引擎本身**永遠 IP 乾淨**，不預載、不內嵌任何真實作品。真實世界由**你在自己 runtime 執行時自帶**（BYO-world）。孵出來的成品引用該世界的專有名詞，那是你自己 runtime 裡的後傳產物。本 repo 散布的只有**引擎**，不含任何特定 IP 的成品。

## 怎麼用

把這個 repo 當作一支 agent skill 安裝（Claude Code、Codex、以及其他支援 skill 的 runtime）：

1. 把整個資料夾放進你的 skills 目錄（例如 Claude Code 的 `~/.claude/skills/apocrypha/`）。
2. 在對話裡說「孵化模擬器」「把《某部作品》做成模擬器」「做一個 XX 的文字遊戲」。
3. 引擎會跟你鎖定世界與玩法，孵出一支可安裝的 GM，問你要不要當場開玩。

引擎內容：

- `SKILL.md` — 編排腦：6 個 phase（定境 → 探源 → 煉核 → 鑄器 → 校境 → 開孵）
- `references/simulator-template.md` — 模擬器骨架 15 區塊填空模板
- `references/immersive-prose-engine.md` — 反 AI 味的沉浸散文鐵律，注入每一支成品

## 取得・了解更多

- **GitHub（這裡）**：從這裡安裝。clone 下來，當 standalone skill 自由使用、修改、散布。
- **llamppost**：了解更多後傳孵化器與 llamppost 的官方資訊，詳見 https://llamppost.ai。

## 授權與標註

MIT License。歡迎自由使用、修改、散布。請依 MIT 條款**保留版權與創作標註**：

> 後傳孵化器 · Apocrypha 由 **llamppost** 創作（https://llamppost.ai）。

© 2026 llamppost
