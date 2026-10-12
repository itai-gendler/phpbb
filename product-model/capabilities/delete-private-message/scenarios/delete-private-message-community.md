---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User confirms removal of the selected ordinary-folder copy, the message’s last remaining copy",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::private-message"
        }
      }
    },
    {
      "text": "The selected mailbox copy and associated notifications are removed and the account counters maintained",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "message-copy",
          "effect": "removes",
          "from": "Available"
        },
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "New message count",
            "Unread message count"
          ]
        },
        {
          "entity": "notification",
          "effect": "removes",
          "from": "Unread"
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::private-message"
        }
      }
    },
    {
      "text": "With no copies remaining, the Product removes the shared private message and dependent attachment",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "private-message",
          "effect": "removes",
          "from": "Sent"
        },
        {
          "entity": "attachment",
          "effect": "removes",
          "with": "private-message",
          "from": "Attached"
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::community::private-message"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_privmsgs.php#delete_pm"
    }
  ]
}
---

# Delete private message — community

## Trigger

The account holder confirms ordinary-folder copy removal when this is the last remaining copy.

## Outcome

The copy and, when no copies remain, shared content/files are removed; counters are maintained and completion schedules the folder.

## Edge cases

- If other copies remain, ordinary-folder deletion removes only the selected owner copy and maintains its counters; the shared content remains.
