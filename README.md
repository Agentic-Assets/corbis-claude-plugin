# Corbis Research Skills plugin for Claude

Corbis is a research workspace for finance, real estate, and economics from Agentic Assets. This plugin connects Claude to the Corbis research connector and adds three skills that turn Corbis tools into cited research workflows. The skills instruct Claude to cite only papers and data that Corbis returns in your conversation or that you supply, so each claim can be traced to a source.

## Skills

- **literature-review** (`/corbis-research-skills:literature-review`): cited literature reviews, "what does research say about" questions, claim checks against published papers, and positioning a paper against related work.
- **citations** (`/corbis-research-skills:citations`): verify and correct BibTeX, flag references that cannot be matched, format citations in APA, MLA, Chicago, or Harvard style, and export BibTeX, Markdown, or JSON.
- **paper-review** (`/corbis-research-skills:paper-review`): referee-style reports and technical audits of a manuscript you provide, with literature positioning and missing-reference checks.

Narrow questions get a quick answer that uses at most five Corbis tool calls, followed by an offer to run the full workflow. Ask for a full review, report, or audit to run the complete procedure.

## Connect

- **claude.ai and Cowork:** after installing the plugin, open its Connectors tab, connect Corbis, and sign in with your Corbis account.
- **Claude Code:** install the plugin, run `/mcp`, choose `corbis`, and complete the browser sign-in.
- **Claude Code with an API key:** if you prefer a key to browser sign-in, create a personal MCP API key in Corbis Settings and add the server yourself. Use this instead of the plugin's connection, not alongside it, and never put a key in the URL.

```bash
claude mcp add --transport http corbis https://www.corbis.ai/api/mcp/universal --header "Authorization: Bearer $CORBIS_MCP_API_KEY"
```

If the Corbis connector is already added another way, such as through the Claude Code research plugin, a custom connector, or a manual `claude mcp add`, Claude sees the same tools twice. Keep one connection: in Claude Code, disable the extra with `/mcp` or `claude plugin disable`.

## Plans

Every skill works on standard Corbis plans. A few optional steps (managed literature synthesis, scored claim verification, and scored referee and audit evaluations) use premium tools that are available on enterprise plans. Without them, the skill says so once and finishes with the standard tools. Tool calls use Corbis credits. Current plans and credit costs: https://www.corbis.ai/pricing

## Data and privacy

The plugin stores nothing. When a skill runs, your research questions, the manuscript excerpts or summaries a tool call needs, and the BibTeX entries you ask it to verify are sent to your Corbis account at www.corbis.ai. Privacy policy: https://www.corbis.ai/privacy

## Scope and limits

Corbis is strongest in finance, real estate, economics, and adjacent business research. Outputs are research aids: check the cited sources before relying on them, and treat the results as inputs to your own judgment, not as investment, legal, or tax advice.

## Support and license

Support: corbis@agenticassets.ai

The plugin files in this repository are MIT licensed. The Corbis service is proprietary and governed by its terms: https://www.corbis.ai/terms
