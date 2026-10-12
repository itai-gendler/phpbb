---
{
  "kind": "edge",
  "routes": {
    "public": "Public browser",
    "community": "Community browser"
  },
  "steps": [
    {
      "text": "The User supplies a file and upload action to the composer.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::posting"
        },
        "community": {
          "place": "forum-web::community::posting"
        }
      }
    },
    {
      "text": "A multipart request reaches the parser although the advertised upload controls are hidden.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::posting"
        },
        "community": {
          "place": "forum-web::community::posting"
        }
      }
    },
    {
      "text": "The uploader stores the file as an Uploaded attachment while the editor’s upload controls remain hidden.",
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
        "public": {
          "place": "forum-web::public::posting"
        },
        "community": {
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

# Add attachment — request with hidden upload controls

## Trigger

A multipart request reaches the parser although the advertised upload controls are hidden.

## Outcome

The submitted file is stored as an Uploaded orphan while advertised controls remain hidden.
