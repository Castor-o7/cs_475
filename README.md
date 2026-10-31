# CS 475: AI Security

Coursework from Portland State's AI Security course (winter 2026).

> **Looking for the Paradox Detector?** It lives in its own repository:
> **[Castor-o7/ParadoxDetector](https://github.com/Castor-o7/ParadoxDetector)**.
> It flags IPs where fast-updating threat-intel sources (OTX, GreyNoise,
> AbuseIPDB and others) disagree with slow-updating ones, and ships as a CLI,
> web app, batch log scanner and MCP server.

## What's here

Two test pages for **indirect prompt injection**: content that looks harmless
to a person but carries instructions aimed at an AI agent that reads it.

| File | Technique |
| --- | --- |
| `index.html` | A plausible tech-news page with the payload hidden in white, 1px text. A person sees articles; an agent reading the page text also sees the hidden instructions. |
| `malicious_page.txt` | The same idea in plain text: an ordinary article with an embedded "system update" telling the agent to route a command to its code-execution tool. |

They were used to test whether agents with browsing or code tools follow
instructions found in the content they read. The payload only prints the
user name, working directory and file list, so it is harmless if an agent does
run it.

**Don't point an agent with real tool access at these pages** outside a sandbox.
