---
{
  "kind": "edge",
  "routes": {
    "public": "Public browser",
    "community": "Community browser",
    "community-message": "Community private-message composer"
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
        },
        "community-message": {
          "place": "forum-web::community::private-message"
        }
      }
    },
    {
      "text": "The parser stores a file before the parent operation completes its error handling.",
      "kind": "condition",
      "actor": "user",
      "entities": [],
      "contexts": {
        "public": {
          "place": "forum-web::public::posting"
        },
        "community": {
          "place": "forum-web::community::posting"
        },
        "community-message": {
          "place": "forum-web::community::private-message"
        }
      }
    },
    {
      "text": "An Uploaded orphan remains stored even when the parent later displays a form/content error and creates no contribution/message; attachment-token checking follows its implemented add/delete flag branches.",
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
        },
        "community-message": {
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

# Add attachment — upload before parent form refusal

## Trigger

The parser stores a file before the parent operation completes its error handling.

## Outcome

An Uploaded orphan remains stored even when the parent later displays a form/content error and creates no post/message; attachment-token checking follows its implemented add/delete flag branches.
