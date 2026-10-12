---
{
  "entities": [
    {
      "entity": "forum",
      "shows": [
        "Name",
        "Description",
        "Rules",
        "Parent",
        "Order",
        "Topic counts",
        "Last contribution"
      ]
    },
    {
      "entity": "category",
      "shows": [
        "Name",
        "Description",
        "Parent",
        "Order",
        "Rules"
      ]
    },
    {
      "entity": "forum-link",
      "shows": [
        "Name",
        "Description",
        "Destination",
        "Track redirects"
      ]
    },
    {
      "entity": "topic",
      "shows": [
        "Subject",
        "Author",
        "Created at",
        "Approved count",
        "Unapproved count",
        "Deleted count",
        "Last contribution"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/index.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/viewforum.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_display.php#display_forums"
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
      "target": "phpBB/includes/acp/acp_forums.php"
    }
  ],
  "entryPoints": [
    {
      "forum-web": "viewforum.php"
    }
  ]
}
---

# Forum

The working context for forum. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
