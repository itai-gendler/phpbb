---
{
  "kind": "primary",
  "routes": {
    "web": "Public browser"
  },
  "steps": [
    {
      "text": "The Guest requests an existing bound contribution file with an enabled extension.",
      "kind": "actor",
      "actor": "guest",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::public::topic"
        }
      }
    },
    {
      "text": "The Product consults attachment Filename, File content, Size, Media classification, Binding",
      "kind": "product",
      "actor": "guest",
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
        "web": {
          "place": "forum-web::public::topic"
        }
      }
    },
    {
      "text": "File bytes are delivered; the ordinary download branch increments Downloads, unlike thumbnail/nonincrementing paths.",
      "kind": "product",
      "actor": "guest",
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
        "web": {
          "place": "forum-web::public::topic"
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

# Download attachment — public

## Trigger

The visitor requests an existing bound post file with an enabled extension.

## Outcome

File bytes are delivered; the ordinary download branch increments Downloads, unlike thumbnail/nonincrementing paths.
