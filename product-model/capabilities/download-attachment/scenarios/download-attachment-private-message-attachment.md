---
{
  "kind": "primary",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User requests the ordinary download of an existing bound message file with an enabled extension.",
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
      "text": "The selected file is bound to a message associated through sender/copy information.",
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
      "text": "The Product consults attachment Filename, File content, Size, Media classification, Binding",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "attachment",
          "effect": "reads",
          "facts": [
            "Filename",
            "File content",
            "Size",
            "Media classification",
            "Binding"
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
      "text": "The bound attachment bytes are delivered and Downloads increments for this ordinary non-thumbnail file response.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "attachment",
          "effect": "changes",
          "facts": [
            "Downloads"
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
      "target": "phpBB/phpbb/storage/controller/attachment.php#handle_attachment"
    }
  ]
}
---

# Download attachment — private message attachment

## Trigger

The selected file is bound to a message associated through sender/copy information; this is a non-thumbnail download with effective display category NONE.

## Outcome

The file is delivered through the private-message download path and its applicable count branch.
