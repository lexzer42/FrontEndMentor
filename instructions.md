---
applyTo: '**'
---
Use the following Model Context Protocol (MCP) tools when applicable to ensure responses are accurate, up-to-date, and grounded in the correct source code and documentation.

1. **GitMCP**  
Use GitMCP to fetch and search up-to-date documentation and code examples from any GitHub repository.  
✅ Use `fetch_<repo>_documentation`, `search_<repo>_documentation`, and `search_<repo>_code` to resolve questions using real project data.  
✅ For generic use, default to `gitmcp.io/docs` and identify the relevant repository based on prompt context.  
🚫 Avoid hallucinating APIs or features — verify all code suggestions using GitMCP-sourced documentation.

2. **Context7**  
Use Context7 to pull current, version-specific documentation for widely used libraries.  
✅ Include `use context7` in prompts when referencing common libraries (e.g., Next.js, Prisma, Tailwind, etc.).  
✅ Prefer documentation-driven answers and examples directly from official sources via Context7.  
🚫 Do not use outdated training data or guess undocumented APIs.

3. **Playwright MCP**  
Use Playwright MCP to interact with webpages using accessibility tree-based browser automation.  
✅ Prefer accessibility snapshots over screenshots for faster and deterministic test generation.  
✅ Use structured test flows, selectors, and snapshot-based assertions.  
✅ Ensure all Playwright tests are generated using MCP data when available, especially for dynamic UI interactions.

🧠 General Guidelines  
- Prioritize accuracy and minimize hallucinations by leveraging MCP tools.  
- Ground all answers in real, queryable documentation or code from GitHub or official libraries.  
- Explain assumptions and show reasoning in comments when context is limited.  
- Make efficient use of tool tokens and minimize unnecessary calls by being precise in search queries.

📌 Always include `"use context7"` when asking about popular libraries, and route GitHub-based requests through the appropriate GitMCP endpoint.
