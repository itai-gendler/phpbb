---
{
  "entities": [
    {
      "entity": "post",
      "shows": [
        "Subject",
        "Content",
        "Author",
        "Guest name",
        "Posted at",
        "Edit information",
        "Visibility",
        "Formatting choices"
      ],
      "collects": [
        "Subject",
        "Content",
        "Guest name",
        "Formatting choices"
      ]
    },
    {
      "entity": "topic",
      "shows": [
        "Subject",
        "Visibility",
        "Last post"
      ]
    },
    {
      "entity": "forum-draft",
      "shows": [
        "Subject",
        "Content",
        "Saved at",
        "Forum",
        "Topic"
      ],
      "collects": [
        "Subject",
        "Content"
      ]
    },
    {
      "entity": "attachment",
      "shows": [
        "Filename",
        "Comment",
        "Size",
        "Media classification"
      ],
      "collects": [
        "File content",
        "Filename",
        "Comment"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/posting.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_posting.php#submit_post"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_posting.php#phpbb_handle_post_delete"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_admin.php#delete_posts"
    },
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
  ],
  "entryPoints": [
    {
      "forum-web": "posting.php"
    }
  ]
}
---

# Posting

The working context for posting. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
