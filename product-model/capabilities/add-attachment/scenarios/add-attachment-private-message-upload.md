---
{
  "kind": "primary",
  "routes": {
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User supplies a file and upload action to the composer.",
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
      "text": "The file is supplied through the admitted private-message composing parser.",
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
      "text": "The uploader stores an Uploaded private-message file without binding it until accepted message submission.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "attachment",
          "effect": "creates",
          "facts": [
            "Filename",
            "File content",
            "Size",
            "Media classification",
            "Comment",
            "Uploader",
            "Uploaded at",
            "Use",
            "Binding",
            "Downloads"
          ],
          "to": "Uploaded"
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
    }
  ]
}
---

# Add attachment — private message upload

## Trigger

The file is supplied through the admitted private-message composing parser.

## Outcome

The uploader stores an Uploaded private-message file without binding it until accepted message submission.
