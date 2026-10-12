---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User requests an existing bound contribution file with an enabled extension.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::topic"
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
        "web": {
          "place": "forum-web::community::topic"
        }
      }
    },
    {
      "text": "File bytes are delivered; the ordinary download branch increments Downloads, unlike thumbnail/nonincrementing paths.",
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
        "web": {
          "place": "forum-web::community::topic"
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

# Download attachment — community

## Trigger

The visitor requests an existing bound post file with an enabled extension.

## Outcome

File bytes are delivered; the ordinary download branch increments Downloads, unlike thumbnail/nonincrementing paths.
