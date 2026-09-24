# Archer MCP Connector

Connect Claude — or any Model Context Protocol client — to your Archer commercial real estate
data. Fifteen read-only tools over properties, underwrites, rent rolls, financials, comparables
and your deal pipeline.

**Server URL**

```
https://app-api.archer.re/mcp
```

## What you need

- An Archer account on the **Pro plan**. On a lower plan the connector signs in successfully but
  shows no tools.
- An MCP client that supports remote servers over Streamable HTTP with OAuth — Claude Desktop,
  Claude Code, and most current MCP clients.

## Connecting

### Claude Desktop

1. Open **Settings → Connectors**.
2. Choose **Add custom connector**.
3. Enter `https://app-api.archer.re/mcp` and confirm.
4. Select **Connect**. Your browser opens; sign in with your Archer credentials and approve the
   consent screen.

If there is no *Add custom connector* option, your Claude organization has disabled custom
connectors. That is an administrator setting, not a problem with the server.

### Claude Code

```bash
claude mcp add --transport http --scope user archer https://app-api.archer.re/mcp
```

Then start Claude Code, run `/mcp`, select **archer**, and choose **Authenticate**. The `add`
command on its own does not sign you in.

### Other MCP clients

This is a standard remote MCP endpoint and is not specific to any one client. It supports
OAuth 2.1 with PKCE, advertising both Dynamic Client Registration and Client ID Metadata
Documents, and speaks protocol revisions `2026-07-28`, `2025-06-18` and `2025-03-26`. Clients
that cannot complete a browser sign-in may instead send an Archer API token as a bearer
credential.

## Signing in

Authentication uses OAuth 2.1. Your Archer password is entered only on Archer's own sign-in page
and is never shared with the MCP client, and Archer never receives your credentials for Claude or
any other client. Access tokens last one hour and refresh automatically. Access is limited to a
single read-only scope, `mcp:read`.

Disconnect the connector in your client at any time to revoke access.

## Tools

All fifteen are read-only. None creates, modifies or deletes anything in your Archer account.

| Tool | Returns |
|---|---|
| Search Properties | Properties matching a name or address |
| Property Details | Full detail for one property |
| Property Location Metrics | Location and market metrics for a property |
| Search Underwrites | Underwrite records, with optional filters |
| Underwrite Details | Full detail for one underwrite |
| Charts of Accounts | Active charts of accounts |
| Rent Roll Dates | The as-of dates with a rent roll on file |
| Rent Roll | Unit-level rent roll for a given date |
| Trailing Twelve Month Availability | The date range of T12 data available |
| Trailing Twelve Month Financials | T12 financial statement data |
| Rent Comparables | Rent comps for a property |
| Sale Comparables | Sale comps for a property |
| Expense Comparables | Expense comps for a property |
| Deal Pipeline Views | Saved pipeline views |
| Deal Pipeline | Deals in your pipeline, filterable and sortable |

## Things you can ask

- "Search Archer for multifamily properties in Austin under 200 units."
- "What does the trailing twelve month financial data look like for property 4821?"
- "Show the unit-level rent roll for that property as of the latest date on file."
- "Which deals in my pipeline are closest to their whisper price?"
- "Pull rent comparables for this property within two miles, built after 1990."

## What the connector can see

Only data already in your own Archer account, and only what your account's permissions allow. It
is scoped to your tenant and cannot reach another customer's data. It exposes the same
information the [documented Archer API](api.html) already returns to you.

## Limits

- 60 requests per minute per credential.
- Tool availability depends on your Archer plan. Below Pro, no tools are listed.

## Troubleshooting

| What you see | What it means |
|---|---|
| Connected, but no tools appear | Your Archer plan is below Pro. |
| You cannot get past the sign-in page | The account does not exist on this environment, or the password is wrong. |
| A request times out | Retry. If it persists, contact support. |
| Rate limit message | You exceeded 60 requests in a minute. Wait and retry. |

## Support

Contact Archer support, or see the [Archer API reference](api.html) for the underlying REST API.
