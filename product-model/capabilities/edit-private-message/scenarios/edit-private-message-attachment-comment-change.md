---
{
  "kind": "primary",
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
      "text": "The sender accepts a comment change on an associated file with message editing.",
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
      "text": "The attachment Comment is saved with the accepted parent edit. The supplied associated Uploaded attachment becomes Attached with this accepted parent.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "private-message",
          "effect": "changes",
          "facts": [
            "Subject",
            "Content",
            "Formatting choices",
            "Edit information",
            "Attachments present"
          ]
        },
        {
          "entity": "attachment",
          "effect": "changes",
          "facts": [
            "Comment",
            "Binding"
          ],
          "from": "Uploaded",
          "to": "Attached"
        }
      ],
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

# Edit private message — attachment comment change

## Trigger

A selected uploaded file accompanies this accepted input. The sender accepts a comment change on an associated file with message editing.

## Outcome

The attachment Comment is saved with the accepted parent edit.
