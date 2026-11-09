# Czechia Legal Research MCP Server (`cz-legal-mcp`)

**[Čeština](#lang-cs) | [English Documentation](#english-documentation)**

---

<a id="lang-cs"></a>
## Právní MCP server pro legislativu a judikaturu ČR (`cz-legal-mcp`) — Čeština

### O tomto repozitáři

Tento repozitář obsahuje Model Context Protocol (MCP) server propojující vaši AI aplikaci (Claude Desktop, Cursor, Windsurf, VS Code / Copilot, Cline nebo Antigravity) přímo se systémem e-Sbírka (`e-sbirka.cz`) a databázemi rozhodnutí okresních, krajských a vrchních soudů (`rozhodnuti.justice.cz`), Nejvyššího soudu (`nsoud.cz`), NSS a Ústavního soudu ČR.

### Rychlá instalace (Výběr AI aplikace)

1. **Stažení:** Klikněte vpravo nahoře na **`<> Code` -> `Download ZIP`** a rozbalte složku v počítači.
2. **Spuštění průvodce:** Dvakrát klikněte na **`Click_Here_To_Install_Windows.bat`** (Windows) nebo **`Click_Here_To_Install_Mac.command`** (macOS).
3. **Výběr AI klienta:** Zaškrtněte používané AI aplikace (Claude, Cursor, Windsurf, VS Code, Antigravity), klikněte na instalovat a restartujte vybranou aplikaci.

**Bezpečnostní poznámka:** Instalátor pracuje výhradně v režimu pro čtení (read-only) a nepřistupuje k žádným vašim osobním souborům.

### Soustava soudů a oficiální zdroje

| Soudní stupeň | Zahrnuté soudy |
|:---|:---|
| **1. stupeň (86 Okresních soudů)** | 86 Okresní soudy (District Courts, plus Obvodní soudy in Prague & Městský soud in Brno) |
| **2. stupeň (8 Krajských a 2 Vrchní soudy)** | 8 Krajských soudů (Regional Courts) & 2 Vrchní soudy (High Courts in Prague and Olomouc) |
| **Nejvyšší soud, NSS a Ústavní soud ČR** | Nejvyšší soud (NS), Nejvyšší správní soud (NSS) & Ústavní soud ČR (NALUS) |

- **e-Sbírka Official Electronic Collection of Laws (e-sbirka.cz):** [https://www.e-sbirka.cz](https://www.e-sbirka.cz) (`e-sbirka.cz`, `zakonyprolidi.cz`, `psp.cz`)
- **Databáze rozhodnutí okresních, krajských a vrchních soudů (rozhodnuti.justice.cz) + NS / NSS / NALUS:** [https://rozhodnuti.justice.cz](https://rozhodnuti.justice.cz) (`nsoud.cz`, `nssoud.cz`, `usoud.cz`, `rozhodnuti.justice.cz`)

---

<a id="english-documentation"></a>
## English Documentation

Model Context Protocol (MCP) server providing live, read-only access to **Czechia (CZ)** legislation, official gazettes, multi-tier judicial decisions (First Instance, Regional/Cantonal/Appellate, and Supreme/Constitutional courts, including HTML and PDF full-text extraction), and statutory citation verification across all major AI clients (**ChatGPT Desktop, OpenAI Codex CLI, Claude Desktop, Claude Code CLI, Cursor, Windsurf, VS Code / GitHub Copilot / Cline / Roo Code, Google Antigravity / Gemini CLI, Perplexity, and Continue.dev**).

---

### Interactive Desktop Setup (Select Your AI Assistant)

This package includes a graphical installer for legal practitioners and non-technical users that lets you select which AI application(s) you use:

1. **Download:** Click **`<> Code`** at the top right of this repository, select **`Download ZIP`**, and extract the folder to your computer.
2. **Run the Setup Utility:**
   - **Windows:** Double-click `Click_Here_To_Install_Windows.bat`
   - **macOS:** Double-click `Click_Here_To_Install_Mac.command`
3. **Select Your AI Client(s) & Connect:** Check the box(es) for the AI assistant(s) installed on your computer (**ChatGPT Desktop & OpenAI Codex CLI**, **Claude Desktop & Claude Code CLI**, **Cursor**, **Windsurf**, **VS Code / GitHub Copilot / Cline / Roo Code**, **Google Antigravity / Gemini CLI**, or **Perplexity / Continue.dev**), click **Install to Selected AI Clients**, and restart your selected AI application.

**System Integrity Note:** The setup utility operates strictly in read-only mode with respect to your personal files and documents. It installs an isolated Python runtime inside the extracted folder and registers the server entry only in the AI client configuration files you select.

---

### Multi-Tier Judicial Hierarchy & Live Indexed National Archives

This server performs live queries across the full judicial hierarchy and official legal archives of **Czechia**, extracting full text from both HTML pages and official court/gazette PDF judgments:

| Judicial Tier | Covered Courts & Tribunals |
|:---|:---|
| **Tier 1 — First Instance** | 86 Okresní soudy (District Courts, plus Obvodní soudy in Prague & Městský soud in Brno) |
| **Tier 2 — Regional / Cantonal / Appellate** | 8 Krajských soudů (Regional Courts) & 2 Vrchní soudy (High Courts in Prague and Olomouc) |
| **Tier 3 — Supreme & Constitutional** | Nejvyšší soud (NS), Nejvyšší správní soud (NSS) & Ústavní soud ČR (NALUS) |

#### Official Portals & Live Indexed Domains

- **National Legislation & Official Gazette:** e-Sbírka Official Electronic Collection of Laws (e-sbirka.cz) — [https://www.e-sbirka.cz](https://www.e-sbirka.cz)
  - *Indexed Legislation Domains:* `e-sbirka.cz`, `zakonyprolidi.cz`, `psp.cz`
- **Court Decisions & Jurisprudence Archives:** Databáze rozhodnutí okresních, krajských a vrchních soudů (rozhodnuti.justice.cz) + NS / NSS / NALUS — [https://rozhodnuti.justice.cz](https://rozhodnuti.justice.cz)
  - *Indexed Judicial & Open Case Law Domains:* `nsoud.cz`, `nssoud.cz`, `usoud.cz`, `rozhodnuti.justice.cz`

---

### Available MCP Tools

| Tool | Description |
|:---|:---|
| `search_legislation` | Searches enacted statutes, codes, decrees, and official gazette publications in Czechia. |
| `search_case_law` | Searches national jurisprudence and open judicial archives for Czechia. |
| `search_tiered_court_decisions` | Filters case law specifically by judicial instance (`first_instance`, `appellate_regional`, `supreme_constitutional`) or specific regional/cantonal/district court. |
| `list_court_hierarchy` | Returns the complete 3-tier court structure and supported regional court filters for Czechia. |
| `get_legal_document_markdown` | Retrieves full statutory or judicial texts (both HTML and official `.pdf` court judgments) and converts them into clean Markdown. |
| `verify_citation` | Validates statutory and case law citations against official registries. |

---

<details>
<summary><b>Manual Configuration for Developers (Optional)</b></summary>

```json
{
  "mcpServers": {
    "cz-legal-mcp": {
      "command": "uvx",
      "args": [
        "--from",
        "https://github.com/jurisatlas/cz-legal-mcp/archive/refs/heads/main.zip",
        "cz-legal-mcp"
      ]
    }
  }
}
```
</details>
