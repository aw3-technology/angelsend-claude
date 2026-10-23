# AngelSend for Claude Code

Run [AngelSend](https://angelsend.ai) from Claude Code: build and launch email
campaigns, import and segment contacts, work your inbox, manage deals and check
analytics, by asking for it.

The `angelsend` plugin bundles:

- the **AngelSend MCP server** (about 200 tools), with sign-in through your
  browser, so there's no key to paste
- the **`angelsend` skill**, which teaches Claude the workflows and AngelSend's
  vocabulary, and makes it ask for your explicit go-ahead before anything is sent

## Install

```
/plugin marketplace add aw3-technology/angelsend-claude
/plugin install angelsend@angelsend
```

Then run `/mcp`, choose **angelsend → Authenticate**, sign in at angelsend.ai
and pick what Claude may do:

| Permission | Allows |
| --- | --- |
| Read | list and fetch anything |
| Write | create and update records, including draft campaigns |
| Delete | delete records |
| Send email | launching campaigns, releasing queued email, test sends, inbox replies |

You can disconnect at any time in angelsend.ai → Settings → API & Security →
Connected AI apps.

## Using an API key instead

```
claude mcp add --transport http angelsend \
  https://invazkujqgdgpkpsingh.supabase.co/functions/v1/mcp-server \
  --header "x-api-key: sk_your_key"
```

Keys are created in Settings → API & Security. With a key, the Write
permission is enough to launch campaigns.

## Try it

- "Build a campaign from https://example.com aimed at seed-stage fintech founders"
- "Who replied to my campaigns this week? Draft answers for the interested ones"
- "How did last month's campaigns perform, and which subject lines won?"

Docs: https://angelsend.ai/docs · Support: will.schulz@aw3.tech
