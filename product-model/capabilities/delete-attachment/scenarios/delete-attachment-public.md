---
{
  "kind": "primary",
  "routes": {
    "web": "Public browser"
  },
  "steps": [
    {
      "text": "The Guest removes a selected uploaded file from composing input.",
      "kind": "actor",
      "actor": "guest",
      "entities": [],
      "contexts": {
        "web": {
          "place": "forum-web::public::posting"
        }
      }
    },
    {
      "text": "The Product removes the selected matching Uploaded attachment and its stored file bytes and drops it from the composing input",
      "kind": "product",
      "actor": "guest",
      "entities": [
        {
          "entity": "attachment",
          "effect": "removes",
          "from": "Uploaded"
        }
      ],
      "contexts": {
        "web": {
          "place": "forum-web::public::posting"
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

# Delete attachment — public

## Trigger

The contributor removes a selected attachment from composing input.

## Outcome

The selected matching Uploaded file and record are removed.

## Edge cases

- Removing a submitted bound post attachment calls deletion immediately; when no files remain, the post/topic attachment flags are cleared. Later parent-text refusal does not undo that file deletion.
