---
{
  "entities": [
    {
      "entity": "topic",
      "shows": [
        "Subject",
        "Author",
        "Visibility",
        "Approved count",
        "Unapproved count",
        "Deleted count",
        "Last contribution"
      ]
    },
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
      ]
    },
    {
      "entity": "attachment",
      "shows": [
        "Filename",
        "Comment",
        "Size",
        "Media classification",
        "File content",
        "Binding"
      ]
    },
    {
      "entity": "bookmark",
      "shows": [
        "Owner",
        "Topic"
      ]
    },
    {
      "entity": "topic-subscription",
      "shows": [
        "Owner",
        "Topic",
        "Notification status"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/viewtopic.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/content_visibility.php#is_visible"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_display.php#watch_topic_forum"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_main.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/storage/controller/attachment.php#handle_attachment"
    }
  ],
  "entryPoints": [
    {
      "forum-web": "viewtopic.php"
    }
  ]
}
---

# Topic

The working context for topic. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
