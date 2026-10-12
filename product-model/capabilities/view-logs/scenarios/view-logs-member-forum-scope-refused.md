---
{
  "kind": "validation",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The Moderator selects grouping container, filters and readable moderated posting area scope.",
      "kind": "actor",
      "actor": "moderator",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::moderator-logs"
        }
      }
    },
    {
      "text": "The requested MCP log scope has no readable moderated posting area entries.",
      "kind": "condition",
      "actor": "moderator",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::moderator-logs"
        }
      }
    },
    {
      "text": "The scoped view is empty/refused rather than disclosing arbitrary posting area logs.",
      "kind": "product",
      "actor": "moderator",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::moderator-logs"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/mcp/mcp_logs.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/acp_logs.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/log/log.php"
    }
  ]
}
---

# View logs — member forum scope refused

## Trigger

The requested MCP log scope has no readable moderated forum entries.

## Outcome

The scoped view is empty/refused rather than disclosing arbitrary forum logs.
