---
name: cz-legal-mcp-skill
description: Official Czechia (CZ) legislation, multi-tier court precedent research, and citation verification skill.
version: 2.0.0
author: JurisAtlas
license: MIT
---

# Czechia Legal Research & Multi-Tier Case Law Skill (`cz-legal-mcp`)

Use this skill whenever the user asks a legal question, drafts a pleading or contract, or researches case law across any judicial instance in **Czechia (CZ)**.

## Verification & Research Rules

1. **Citation Verification:** Never fabricate a statutory provision or case citation. Query `search_legislation`, `search_case_law`, `search_tiered_court_decisions`, or `verify_citation` before citing any authority (e.g., `ECLI:CZ:NS:2024:21.CDO.123.2023.1 or 89/2012 Sb.`).
2. **Multi-Tier Judicial Coverage:**
   - **First Instance (Trial / Municipal / District):** 86 Okresní soudy (District Courts, plus Obvodní soudy in Prague & Městský soud in Brno)
   - **Second Instance (Cantonal / Regional / Appellate):** 8 Krajských soudů (Regional Courts) & 2 Vrchní soudy (High Courts in Prague and Olomouc)
   - **Supreme & Constitutional Instance:** Nejvyšší soud (NS), Nejvyšší správní soud (NSS) & Ústavní soud ČR (NALUS)
   - **Primary Tiered Database:** Databáze rozhodnutí okresních, krajských a vrchních soudů (rozhodnuti.justice.cz) + NS / NSS / NALUS (`https://rozhodnuti.justice.cz`)
