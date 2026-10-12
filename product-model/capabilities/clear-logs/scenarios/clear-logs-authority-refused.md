---
{
  "kind": "validation",
  "routes": {
    "community": "Community browser",
    "administration": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator confirms selected or whole-grouping container log removal in the admitted scope.",
      "kind": "actor",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::moderator-logs"
        },
        "administration": {
          "place": "forum-web::administration::logs"
        }
      }
    },
    {
      "text": "The log removal reaches its authority-refusal branch.",
      "kind": "condition",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::moderator-logs"
        },
        "administration": {
          "place": "forum-web::administration::logs"
        }
      }
    },
    {
      "text": "No entries are removed.",
      "kind": "product",
      "actor": "administrator",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::moderator-logs"
        },
        "administration": {
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

# Clear logs — authority refused

## Trigger

The log removal reaches its authority-refusal branch.

## Outcome

No entries are removed.
