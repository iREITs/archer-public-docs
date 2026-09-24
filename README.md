# Archer Developer Documentation

Reference material for Archer's public interfaces: the REST API, and the Model Context Protocol
connector that lets AI assistants read your Archer data.

<div class="cards">
  <a class="card" href="api.html">
    <b>REST API reference →</b>
    <span>The full OpenAPI reference for the Archer public API — properties, underwrites, rent rolls, financials and comparables.</span>
  </a>
  <a class="card" href="#/mcp">
    <b>MCP connector →</b>
    <span>Connect Claude or any MCP client to your Archer account. Fifteen read-only tools, OAuth sign-in, no local install.</span>
  </a>
  <a class="card" href="#/privacy">
    <b>Connector privacy policy →</b>
    <span>What the MCP connector accesses, what Archer records, how long it is kept, and what leaves via your AI client.</span>
  </a>
</div>

## Quick start

Connect an MCP client to Archer in one command:

```bash
claude mcp add --transport http --scope user archer https://app-api.archer.re/mcp
```

Then run `/mcp`, select **archer**, and choose **Authenticate**. See the
[MCP connector guide](#/mcp) for Claude Desktop and other clients.

For the REST API, start with the [API reference](api.html).

## Getting help

Contact Archer support with your account details and, where relevant, the request identifier
returned with an error.
