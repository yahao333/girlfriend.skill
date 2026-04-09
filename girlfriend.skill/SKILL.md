---
name: girlfriend
description: "Distill a girlfriend's personality, advice style, and companionship spirit into an AI Skill. | 蒸馏闺蜜的性格、建议风格和陪伴精神到一个 AI Skill 中。"
argument-hint: "[girlfriend-name-or-slug]"
version: "1.0.0"
user-invocable: true
allowed-tools: Read, Write, Edit, Bash
---

# 闺蜜.skill 创建器（Claude Code 版）

## 触发条件

当用户说以下任意内容时启动：
- `/girlfriend`
- "帮我创建一个闺蜜 skill"
- "我想蒸馏闺蜜"
- "新建闺蜜"
- "给我做一个闺蜜的 skill"

---

## 主流程：创建新闺蜜 Skill

### Step 1：基础信息录入

问 3 个问题：

1. **称呼**（必填）：你平时怎么称呼她？如「闺蜜」「姐妹」「宝」
2. **基本信息**（一句话）：年龄、星座/性格、职业、特点
   - 示例：`28岁，天蝎座，自由职业毒舌但暖心擅长安慰人`
3. **特别记忆**（可选）：你们之间最经典的一件事、一个梗或一段对话

### Step 2：原材料导入

询问用户提供原材料：

```
原材料怎么提供？

  [A] 微信聊天记录
      私聊记录、闺蜜群

  [B] 朋友圈/小红书
      她发布的内容、评论互动

  [C] 语音消息
      她的语音条风格、口头禅

  [D] 合照/截图
      有意义的照片、聊天截图

  [E] 直接粘贴
      复制文字粘贴进来

可以混用，也可以跳过（仅凭手动信息生成）。
```

### Step 3：分析生成

将收集到的材料按三条线分析：

**线路 A（说话风格）**：
- 毒舌/暖心比例：嘴上不饶人但心里在乎
- 用词习惯：口头禅、标点符号用法
- 表达方式：直接 vs 委婉，吐槽 vs 认真

**线路 B（安慰方式）**：
- 安慰套路：骂醒你 vs 陪你哭 vs 给你分析
- 倾听方式：认真听 vs 心不在焉陪伴
- 建议风格：给方法 vs 给情绪价值

**线路 C（社交能力）**：
- 八卦能力：消息灵通程度
- 社交圈：她带你认识的人
- 特殊技能：美妆、穿搭、情感专家

### Step 4：确认并写入

向用户展示摘要，确认后写入文件到 `./girlfriends/{slug}/`。

---

## 进化模式

用户追加新材料时，分析增量内容并 merge 到对应部分。

用户纠正时说「她不会这样」「她应该是」，更新对应内容。

---
---

# Girlfriend.skill Creator (Claude Code Edition)

## Trigger Conditions

Activate when the user says:
- `/girlfriend`
- "Help me create a girlfriend skill"
- "I want to distill my bestie"
- "New bestie"

---

## Main Flow: Create a New Girlfriend/Bestie Skill

### Step 1: Basic Info (3 questions)

1. **Name/Nickname** (required): What do you call her? e.g., "Bestie", "Sis", "Babe"
2. **Basic Info** (one sentence): Age, zodiac sign/personality, occupation, traits
   - Example: `28 years old, Scorpio, freelancer, savage but warm, great at comforting people`
3. **Special Memories** (optional): The most iconic thing, inside joke, or conversation between you two

### Step 2: Source Materials

```
How would you like to provide materials?

  [A] WeChat chat records
      Private chats, bestie group chats

  [B] Moments/RED posts
      Her posts, comments, interactions

  [C] Voice messages
      Her voice note style, catchphrases

  [D] Photos/screenshots
      Meaningful photos, chat screenshots

  [E] Paste text
      Copy-paste directly
```

### Step 3: Analyze & Generate

Analyze collected materials along three tracks:

**Track A (Speaking Style)**:
- Savage/warm ratio: Tough love but cares deeply
- Word choices: Catchphrases, punctuation habits
- Expression approach: Direct vs subtle, roasting vs serious

**Track B (Comfort Style)**:
- Comforting套路: Scolds you awake vs cries with you vs gives analysis
- Listening style: Attentive vs distracted companionship
- Advice style: Practical solutions vs emotional support

**Track C (Social Skills)**:
- Gossip ability: How well-connected she is
- Social circle: People she introduced you to
- Special skills: Beauty, fashion, relationship expert

### Step 4: Confirm & Write

Show summary to user, write files to `./girlfriends/{slug}/` after confirmation.

---

## Evolution Mode

When user adds new materials, analyze delta and merge into relevant sections.

When user corrects with "she wouldn't do that" / "they should be", update content.
