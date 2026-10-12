---
{
  "entities": [
    {
      "entity": "forum",
      "shows": [
        "Name",
        "Description",
        "Parent",
        "Order",
        "Rules",
        "Password protection",
        "Posting status",
        "Posting options",
        "Post review",
        "Post-count policy",
        "Topic counts",
        "Last contribution",
        "Pruning settings"
      ],
      "collects": [
        "Name",
        "Description",
        "Parent",
        "Order",
        "Rules",
        "Password protection",
        "Posting status",
        "Posting options",
        "Post review",
        "Post-count policy",
        "Pruning settings"
      ]
    },
    {
      "entity": "category",
      "shows": [
        "Name",
        "Description",
        "Parent",
        "Order",
        "Rules",
        "Password protection"
      ],
      "collects": [
        "Name",
        "Description",
        "Parent",
        "Order",
        "Rules",
        "Password protection"
      ]
    },
    {
      "entity": "forum-link",
      "shows": [
        "Name",
        "Description",
        "Parent",
        "Order",
        "Rules",
        "Password protection",
        "Destination",
        "Track redirects",
        "Redirect count"
      ],
      "collects": [
        "Name",
        "Description",
        "Parent",
        "Order",
        "Rules",
        "Password protection",
        "Destination",
        "Track redirects"
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
      "forum-web": "adm/index.php?i=forums&mode=manage&action=edit"
    }
  ]
}
---

# Forum

The working context for forum. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
