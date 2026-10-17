# Skill Discovery, Registry & Update Directory

This directory maintains the catalog of all specialized skills hosted in `PINNACLEAISOLUTIONS/master-deluxe-skill` that can be imported directly into nanoMuse on Android.

---

## 📦 Live Repository Skill Registry

To import any of these into nanoMuse on your phone:
1. Tap **Settings (⚙️) ➔ Skills Management ➔ `+` (Add)**.
2. Select the **URL / GitHub** tab.
3. Paste the corresponding GitHub link below and tap **Import**.

| Skill Name | Purpose & Capabilities | 1-Tap nanoMuse Import URL |
|---|---|---|
| **`master-deluxe`** | Complete executive super-agent orchestrating all 12 pillars with neural memory. | `https://github.com/PINNACLEAISOLUTIONS/master-deluxe-skill/tree/main` |
| **`skill-finder`** | Autonomous skill discovery, repo indexing, GitHub search, and import link generator. | `https://github.com/PINNACLEAISOLUTIONS/master-deluxe-skill/tree/main/skills/skill-finder` |
| **`lead-sniper`** | Google Maps business scraper, direct email/phone enrichment, Facebook lead extractor. | `https://github.com/PINNACLEAISOLUTIONS/master-deluxe-skill/tree/main/skills/lead-sniper` |
| **`growth-copywriter`** | Eugene Schwartz awareness stages, Jobs-to-be-Done (JTBD), loss aversion, objection killer. | `https://github.com/PINNACLEAISOLUTIONS/master-deluxe-skill/tree/main/skills/growth-copywriter` |
| **`clean-code-engineer`** | Software architecture, SRP/KISS/YAGNI, early-return guard clauses, TDD red-green-refactor. | `https://github.com/PINNACLEAISOLUTIONS/master-deluxe-skill/tree/main/skills/clean-code-engineer` |
| **`systematic-debugger`** | Root-cause isolation, error trace dissection, zero symptom patching, regression testing. | `https://github.com/PINNACLEAISOLUTIONS/master-deluxe-skill/tree/main/skills/systematic-debugger` |
| **`cloud-architect`** | Supabase SQL & RLS, Neon serverless branching, Cloudflare Workers, Zapier 6,000+ app pipelines. | `https://github.com/PINNACLEAISOLUTIONS/master-deluxe-skill/tree/main/skills/cloud-architect` |
| **`deep-researcher`** | Perplexity-grade multi-source corroboration, epistemic truth hierarchy, citation tracking. | `https://github.com/PINNACLEAISOLUTIONS/master-deluxe-skill/tree/main/skills/deep-researcher` |

---

## 🔍 How the Bot Searches for New Skills

When you ask the bot to *"find skills for [topic]"*:
1. **Local Repository Check**: It first checks this registry to see if a dedicated skill already exists.
2. **Community & GitHub Discovery**: If the topic requires a specialized external skill (e.g. crypto analysis, Kubernetes, Flutter, image generation, legal contracts), it uses GitHub Search and Fetch to search open-source skill hubs:
   - `https://github.com/OpenMinis/MinisSkills`
   - `https://github.com/muratcankoylan/Agent-Skills-for-Context-Engineering`
   - `https://github.com/anthropics/anthropic-tools`
3. **Instant Skill Synthesis**: If no pre-built skill exists, the bot autonomously generates a production-grade `SKILL.md` with valid YAML frontmatter, displays it for you, and offers to push it directly to your GitHub repository!
