---
{
  "kind": "primary",
  "routes": {
    "web": "Administration browser"
  },
  "steps": [
    {
      "text": "The reviewing person selects grouping container, filters and readable moderated posting area scope.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::administration::logs"
        }
      }
    },
    {
      "text": "Matching actor-visible entries are displayed.",
      "kind": "product",
      "actor": "administrator",
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
          "place": "forum-web::administration::logs"
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

# View logs — administration

## Trigger

The moderator selects category, filters and readable moderated forum scope.

## Outcome

Matching actor-visible entries are displayed.
