---
{
  "kind": "validation",
  "routes": {
    "community": "Community browser",
    "administration": "Administration browser"
  },
  "steps": [
    {
      "text": "The Administrator requests removal of the selected entries.",
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
      "text": "The removal selection lacks completed confirmation.",
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
      "text": "Confirmation is displayed and no selected entries are removed at this stage.",
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

# Clear logs — unconfirmed removal

## Trigger

The removal selection lacks completed confirmation.

## Outcome

Confirmation is displayed and no selected entries are removed at this stage.
