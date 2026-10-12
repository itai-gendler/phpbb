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
        "Order"
      ]
    },
    {
      "entity": "forum-link",
      "shows": [
        "Name",
        "Description",
        "Parent",
        "Order"
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
      "target": "phpBB/ucp.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions.php#login_box"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/auth/provider/db.php#login"
    }
  ],
  "entryPoints": [
    {
      "forum-web": "index.php"
    }
  ]
}
---

# Board index

The working context for board index. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
