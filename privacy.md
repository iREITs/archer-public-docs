# Archer MCP Connector — Privacy Policy

How the Archer MCP connector handles data. This policy covers the connector at
`https://app-api.archer.re/mcp` only. Use of the Archer platform generally is governed by
Archer's main privacy policy and terms.

## What the connector accesses

When you connect an MCP client to Archer and approve the consent screen, the client is granted
read-only access to data already held in your own Archer account. Depending on which tool it
calls, that may include:

- Property records and their details, including location and market metrics.
- Underwrite records and their calculated outputs.
- Unit-level rent rolls and the dates on which they were recorded.
- Trailing-twelve-month financial statement data and charts of accounts.
- Rent, sale and expense comparables.
- Deal pipeline records. **These can include commercially sensitive fields** such as whisper and
  purchase prices, returns, deal-stage notes, and the names, email addresses and telephone
  numbers of brokers associated with a deal.

The connector is scoped to your own tenant and cannot reach another customer's data. It exposes
no information that the documented Archer API does not already return to the same account.

## What the connector cannot do

Every tool is read-only. The connector cannot create, modify or delete anything in your Archer
account. It is granted a single scope, `mcp:read`, and no other.

It does not read your conversation history, your MCP client's memory, or any files you have not
explicitly asked a tool to act on.

## Authentication and credentials

Sign-in uses OAuth 2.1 with PKCE. Your Archer password is entered only on Archer's own sign-in
page and is never shared with the MCP client. Archer does not receive your credentials for Claude
or any other client.

Access tokens are valid for one hour; refresh tokens are rotated on use. You can revoke access at
any time by disconnecting the connector in your MCP client, which invalidates its tokens.

## What Archer records

Archer logs each request to the connector for security, debugging and abuse prevention. A log
entry contains:

- A request identifier, and the identifiers of the account and user making the request.
- The HTTP method, path and route.
- Query parameters and the request body — for a tool call, this includes the arguments supplied,
  such as a property identifier or a search term.
- The response status, size and duration, and any error.
- The originating IP address, user agent and referrer.

Archer does not log the content of responses, and does not record the conversation that led to a
tool call.

## Retention

Request logs are retained for **six months** and then deleted.

The underlying commercial real estate data is your own Archer account data and is retained
according to your agreement with Archer, independently of the connector.

## Sharing with third parties

When you use the connector, the data a tool returns is sent to the MCP client you connected — for
example Claude, operated by Anthropic. Once it reaches that client it is handled under that
provider's own terms and privacy policy, not Archer's. You choose which client to connect and
which questions to ask.

Archer does not sell your data, and does not share it with any other third party as part of the
connector's operation.

## Where data is processed

The connector runs on Archer's existing production infrastructure and processes data in the same
environment as the rest of the Archer platform.

## Your choices

- Do not connect the connector, and none of the above applies.
- Disconnect at any time from your MCP client to revoke access.
- Ask Archer support about access to, or deletion of, your account data.

## Contact

Questions about this policy, or about data handled by the connector:
[privacy@archer.re](mailto:privacy@archer.re).

---

*Last updated 24 September 2026.*
