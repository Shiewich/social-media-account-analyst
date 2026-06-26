---
name: social-media-account-analyst
description: Analyze Chinese social-media account backend exports, especially Xiaohongshu and Douyin data, to diagnose account positioning, content pillars, post performance, trend-fit opportunities, and next-video strategy. Use when the user provides Xiaohongshu note lists, Douyin creator-center exports, screenshots, CSV/XLSX files, or asks for content-account analysis, section/pillar strategy, topic selection, next post recommendations, or a dopamine-color dashboard/report for self-media operations.
---

# Social Media Account Analyst

## Overview

Use this skill to act as a senior Chinese self-media operator. Analyze account backend data, split the account into content pillars, explain what is working, and recommend the next posts with platform-specific execution details.

The first supported platforms are Xiaohongshu and Douyin. Treat Bilibili and WeChat Channels as future extensions unless the user provides explicit fields and asks for exploratory analysis.

## Workflow

1. Confirm available inputs: account name, platform, export file or screenshot, date range, follower count, account goal, target audience, monetization mode, and known content pillars.
2. Load platform-specific field guidance from `references/platform-fields.md` when mapping backend columns or screenshots.
3. Run `scripts/analyze_account_data.py` for CSV/XLSX inputs when possible. Use its JSON/Markdown/HTML outputs as analytical scaffolding, then add senior-operator judgment.
4. Load `references/analysis-framework.md` before writing conclusions or next-post recommendations.
5. Load `references/ui-output.md` when producing HTML, screenshots, report layouts, or visual dashboard guidance.
6. If the user asks for current strategy, perform or request a fresh trend scan. Do not hard-code stale hot topics. Use current platform hot lists, search suggestions, industry news, competitor examples, and user-provided trend notes.
7. Separate historical proof from strategic inference. Say when a recommendation is based on data, when it is based on current trends, and when it is a creative hypothesis.

## Output Defaults

Prefer a two-layer deliverable:

- A decision report in Markdown/Docx/PDF style for durable review.
- A flat dopamine-color HTML dashboard for quick scanning and screenshots.

For each major content pillar, include:

- Current role in the account: traffic, conversion, trust, monetization, community, or experimental.
- Key evidence: top posts, weak posts, engagement shape, follower conversion, utility ratio, and trend fit.
- Decision: scale, repackage, test, pause, merge, or split into a new pillar.
- Next-post plan: topic, title direction, cover hook, first 3 seconds, structure, CTA, and success metric.

## Operating Rules

- Prioritize actionable strategy over descriptive dashboards.
- Avoid judging only by total views. Cross-check exposure, click/read or play, completion, interaction, saves, shares, comments, and follower conversion.
- Treat Xiaohongshu as search/collection/community-intent first; treat Douyin as recommendation-flow/retention/follower-conversion first.
- Mark data gaps explicitly. If there is no follower count, completion rate, cover click rate, or impression data, avoid pretending precision.
- Use Chinese account-operation language in user-facing outputs unless the user requests another language.
- Keep recommendations concrete enough that a creator can shoot the next post without another planning round.

## Bundled Resources

- `references/platform-fields.md`: field mapping and platform-specific metric interpretation.
- `references/analysis-framework.md`: pillar diagnosis, trend scan, strategy matrix, and report structure.
- `references/ui-output.md`: dopamine flat UI rules, palette, and dashboard layout.
- `scripts/analyze_account_data.py`: CSV/XLSX summarizer that generates JSON, Markdown, and HTML drafts.
