---
{
  "kind": "primary",
  "routes": {
    "web": "Community browser"
  },
  "steps": [
    {
      "text": "The User requests removal of the last attached file in the contribution editor with a valid file-action form.",
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
      "text": "The Product removes the Attached attachment immediately, drops it from composing input and clears the post and topic attachment flags when no bound files remain.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "attachment",
          "effect": "removes",
          "from": "Attached"
        },
        {
          "entity": "post",
          "effect": "changes",
          "facts": [
            "Attachments present"
          ]
        },
        {
          "entity": "topic",
          "effect": "changes",
          "facts": [
            "Attachments present"
          ]
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

# Delete attachment — community

## Trigger

The contributor removes the last bound attachment from an admitted post editor using a valid attachment-action form.


## Outcome

The file is removed immediately and the Post/Topic attachment flags are synchronized; later acceptance of proposed parent text is not required.


## Edge cases
- Removing a submitted bound post attachment calls deletion immediately; when no files remain, the post/topic attachment flags are cleared. Later parent-text refusal does not undo that file deletion.
- Removing a matching Uploaded orphan deletes its bytes and record without a bound-parent flag update.
