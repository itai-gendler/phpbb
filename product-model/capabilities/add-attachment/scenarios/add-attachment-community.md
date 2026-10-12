---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User supplies a file and upload action to the composer.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::community::posting"
        }
      }
    },
    {
      "text": "The uploader stores bytes and metadata as an Uploaded attachment, unattached until accepted parent submission.",
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
        "web": {
          "place": "forum-web::community::posting"
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

# Add attachment — community

## Trigger

The contributor supplies a supported file to the posting parser.

## Outcome

The uploader stores bytes and metadata as an Uploaded attachment, unattached until accepted parent submission.
