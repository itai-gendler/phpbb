---
{
  "kind": "primary",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User requests removal of the last attached file from the message editor with the supplied file action form",
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
      "text": "The sender removes an uploaded file through the message composer.",
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
      "text": "The Product removes the Attached attachment immediately, drops it from the composing input and clears the private message attachment flag when no bound files remain",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "attachment",
          "effect": "removes",
          "from": "Attached"
        },
        {
          "entity": "private-message",
          "effect": "changes",
          "facts": [
            "Attachments present"
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
      "target": "phpBB/includes/message_parser.php#parse_attachments"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/attachment/upload.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/attachment/delete.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/attachment/resync.php"
    }
  ]
}
---

# Delete attachment — private message attachment

## Trigger

The sender removes an attachment through the message composer.

## Outcome

The Attached file is removed immediately and, when it was the last bound file, the message’s attachment flag is cleared. A subsequent refused text edit does not undo this removal.
