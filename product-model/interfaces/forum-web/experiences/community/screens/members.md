---
{
  "entities": [
    {
      "entity": "account",
      "shows": [
        "Username",
        "Joined at",
        "Post count",
        "Profile values",
        "Last active at"
      ]
    },
    {
      "entity": "group",
      "shows": [
        "Name",
        "Type"
      ]
    },
    {
      "entity": "group-membership",
      "shows": [
        "Account",
        "Group",
        "Default"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/memberlist.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/functions_display.php#phpbb_show_profile"
    }
  ],
  "entryPoints": [
    {
      "forum-web": "memberlist.php"
    }
  ]
}
---

# Members

The working context for members. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
