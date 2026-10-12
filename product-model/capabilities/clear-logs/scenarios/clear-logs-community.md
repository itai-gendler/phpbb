---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The Administrator confirms selected or whole-grouping container log removal in the admitted scope.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::moderator-logs"
        }
      }
    },
    {
      "text": "Selected entries are removed; entries outside the grouping container/scope remain.",
      "kind": "product",
      "actor": "administrator",
      "entities": [
        {
          "entity": "log-entry",
          "effect": "removes"
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

# Clear logs — community

## Trigger

The administrator confirms selected or whole-category log removal in the admitted scope.

## Outcome

Selected entries are removed; entries outside the category/scope remain.
