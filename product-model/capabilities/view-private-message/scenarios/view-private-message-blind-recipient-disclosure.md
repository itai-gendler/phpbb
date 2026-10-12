---
{
  "kind": "primary",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User opens the selected Outbox item addressed through To and blind-copy fields.",
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
      "text": "The selected sent item addresses both individuals and groups through To and blind-copy fields.",
      "kind": "condition",
      "actor": "user",
      "entities": [
        {
          "entity": "private-message",
          "effect": "reads",
          "facts": [
            "To recipients",
            "Blind-copy recipients"
          ]
        },
        {
          "entity": "group",
          "effect": "reads",
          "facts": [
            "Name"
          ]
        }
      ],
      "contexts": {
        "community": {
          "place": "forum-web::community::private-message"
        }
      }
    },
    {
      "text": "The private message displays its To and blind-copy addressing, including the sender’s addressed individuals and group names.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "private-message",
          "effect": "reads",
          "facts": [
            "To recipients",
            "Blind-copy recipients"
          ]
        },
        {
          "entity": "group",
          "effect": "reads",
          "facts": [
            "Name"
          ]
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
      "target": "phpBB/includes/ucp/ucp_pm_viewmessage.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_privmsgs.php#update_unread_status"
    }
  ]
}
---

# View private message — blind recipient disclosure

## Trigger

The sender opens their Outbox message containing individual and group To and blind-copy recipients.


## Outcome

The sender’s addressing projection displays the addressed individuals and groups. Recipient-side views return their filtered projection; excluded blind names are absent.
