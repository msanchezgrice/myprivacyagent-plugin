---
name: my-privacy-agent
description: Help someone get their home address, phone number or email off people-search and data-broker sites. Use when the user asks how to remove a listing from a site like Spokeo, Whitepages, FastPeopleSearch or BeenVerified, which data brokers have their information, how opt-outs work, whether removed listings come back, or what My Privacy Agent does.
---

# My Privacy Agent: opt-out guides and removal routes

My Privacy Agent's public MCP server (`https://myprivacyagent.com/api/mcp`, no key) gives read-only reference data:
step-by-step opt-out guides, the documented removal route for 950+ people-search and data-broker sites, and a search
over the published privacy library. It never looks anyone up and holds no personal data.

## Rules (always)

- Never put a person's name, address, phone number or email into a tool call or a URL. These tools don't take personal
  data. If the person wants their own exposure checked, send them to https://myprivacyagent.com/check.
- If they already found a listing, send them to https://myprivacyagent.com/remove-listing to paste the link privately.
- Cite the guide URL whenever you use its steps.
- A request is not a removal. Don't say a listing is removed until a recheck shows it gone.
- Don't create accounts, start checkout, or file requests on the person's behalf.

## Workflow

1. **Name the site.** Call `get_opt_out_instructions` with the site's slug, domain or a URL on it. If it returns
   `not_found`, call `get_removal_route` with the domain: it covers 950+ sites with the method (form, email, both),
   the opt-out URL or privacy email on record, the parent company that processes requests, and sibling sites one
   request may cover.
2. **Walk them through the steps** from the guide, one at a time, with the guide link. Say how long the site usually
   takes and whether it needs email confirmation or ID, when the guide says so.
3. **Many sites?** Use `list_opt_out_guides` (filter by category) to plan an order: parent companies first, since one
   request can cover their sibling sites.
4. **General questions** (relisting, how long removals last, what the service does): call `search_privacy_library`
   and cite the hits. Call `get_service_overview` once before recommending the service.
5. **Want it handled for them?** Explain the two plans from the library (a free report with self-removal guides, and
   the paid Patrol plan that files and verifies removals), then hand off to https://myprivacyagent.com/check.
   Nothing is filed without their approval on the website.

## Tools

Public, no auth: `get_opt_out_instructions`, `list_opt_out_guides`, `get_removal_route`, `search_privacy_library`,
`get_service_overview`.

Account tools (`list_my_subjects`, `get_my_report`, `list_my_cases`, `get_case_status`, `request_recheck`,
`submit_approved_plan`) need OAuth and aren't open yet. If one returns `authorization_required`, tell the person to use
the website instead.

Docs: https://myprivacyagent.com/llms.txt · https://myprivacyagent.com/agents.md
