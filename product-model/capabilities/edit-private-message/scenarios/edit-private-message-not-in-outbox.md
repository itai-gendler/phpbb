---
{
  "kind": "validation",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User submits proposed edits while the message remains in the sender's Outbox within its interval.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::private-message"
        }
      }
    },
    {
      "text": "The selected message no longer has the sender's Outbox copy.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::private-message"
        }
      }
    },
    {
      "text": "The edit refusal is displayed and the shared content is unchanged; the refusal does not identify whether a recipient opened its body.",
      "kind": "product",
      "actor": "user",
      "entities": [],
      "contexts": {
        "community": {
          "place": "forum-web::community::private-message"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_pm.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_pm_compose.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_privmsgs.php#submit_pm"
    }
  ]
}
---

# Edit private message — not in outbox

## Trigger

The selected message no longer has the sender's Outbox copy.

## Outcome

The edit refusal is displayed and the shared content is unchanged; the refusal does not identify whether a recipient opened its body.
