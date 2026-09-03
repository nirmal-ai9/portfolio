<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0F172A,100:1E293B&height=200&section=header&text=hurttlocker&fontSize=60&fontColor=38BDF8&animation=fadeIn&fontAlignY=38&desc=Building%20memory%20and%20control%20layers%20for%20AI%20agents&descAlignY=58&descSize=18" width="100%"/>

<a href="https://github.com/hurttlocker">
  <img src="https://readme-typing-svg.demolab.com/?font=JetBrains+Mono&size=22&duration=3000&pause=1000&color=38BDF8&center=true&vCenter=true&width=600&lines=Import-first%2C+zero-dependency+memory+for+AI+agents;Building+cortex+%E2%80%94+observable+recall%2C+not+a+black+box;Building+o8+%E2%80%94+one+governed+control+plane+for+coding+agents;MCP+%2F+Go+%2F+CLI+tooling" alt="Typing SVG" />
</a>

<br/>

<img src="https://img.shields.io/badge/focus-AI%20agent%20infrastructure-38BDF8?style=for-the-badge&labelColor=0F172A" />
<img src="https://img.shields.io/badge/license-MIT-22C55E?style=for-the-badge&labelColor=0F172A" />
<img src="https://img.shields.io/badge/status-actively%20shipping-F59E0B?style=for-the-badge&labelColor=0F172A" />

</div>

<br/>

## About

I build infrastructure that sits underneath AI agents — the memory they recall from and the control plane that governs what they're allowed to do. Two projects anchor that work:

- **[`cortex`](https://github.com/hurttlocker/cortex)** — a memory layer agents import into, search, and connect to over MCP
- **[`o8`](https://github.com/hurttlocker/o8)** — a governed control room that routes every client (desktop, mobile, CLI, MCP) through the same review and approval gates

Shared philosophy across both: one source of truth, observable state, no black boxes.

<br/>

## Featured projects

<table>
<tr>
<td width="50%" valign="top">

### 🧠 [cortex](https://github.com/hurttlocker/cortex)
**Import-first, zero-dependency, observable memory layer for AI agents**

Agents get persistent memory through 17 MCP tools — search, import, and fact-first retrieval, all working fully offline with no API keys required.

```bash
# Setup — auto-detects your LLM keys + Ollama
cortex init

# Import your files
cortex import ~/notes/ --recursive --extract

# Search your knowledge
cortex search "what did I decide about the API design"

# Connect to your agent
claude mcp add cortex -- cortex mcp
```

`Go` `MCP` `BM25 search` `1,081 tests / 15 packages` `MIT`

Connectors: GitHub · Gmail · Calendar · Drive · Slack · Discord · Telegram · Notion

</td>
<td width="50%" valign="top">

### 🕹️ [o8](https://github.com/hurttlocker/o8)
**The open-source control room for coding agents**

Desktop, mobile, the CLI, and any MCP client all reach the same missions, packet reviews, approvals, and audit trail — one governed control plane, one live state, one review path.

```bash
gh repo fork hurttlocker/o8 --clone
cd o8 && npm install
npm run dev
```

`CLI + MCP` `Desktop / Mobile clients` `MIT`

One shared audit trail across every surface that touches an agent's actions.

</td>
</tr>
</table>

<br/>

## Recent activity on cortex

| Release | Highlights |
|---|---|
| **v1.3.0** | Import-time denylist, quality profiles, source-tier-aware ranking, fact-first retrieval (`cortex search --facts`) |
| **v1.2.4** | Bounded grouped recall packing, collapsed-hit detail markers |
| **#379** | Source titles carried into graph exports for consistent citations |
| **#312** | Read-only trust visibility for multi-agent trust boundaries |
| **#241** | Unified config resolver — `config.yaml` → env → CLI, with provenance in `cortex doctor` |

<br/>

## Tech stack

<div align="center">

<img src="https://skillicons.dev/icons?i=go,js,ts,nodejs,git,github,bash,vim&theme=dark" />

</div>

<br/>

## GitHub stats

<div align="center">
  
<img src="https://github-readme-streak-stats.herokuapp.com/?user=hurttlocker&theme=tokyonight&hide_border=true" height="165"/>

</div>

<br/>

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1E293B,100:0F172A&height=120&section=footer"/>

</div>
