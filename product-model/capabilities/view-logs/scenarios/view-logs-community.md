---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The Moderator selects grouping container, filters and readable moderated posting area scope.",
      "kind": "actor",
      "actor": "moderator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::moderator-logs"
        }
      }
    },
    {
      "text": "Matching actor-visible entries are displayed.",
      "kind": "product",
      "actor": "moderator",
      "entities": [
        {
          "entity": "log-entry",
          "effect": "reads",
          "facts": [
            "Actor",
            "Operation",
            "Recorded at",
            "IP",
            "Category",
            "Subject",
            "Event information"
          ]
        }
      ],
      "contexts": {
        "web": {
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

# View logs — community

## Trigger

The moderator selects category, filters and readable moderated forum scope.

## Outcome

Matching actor-visible entries are displayed.
