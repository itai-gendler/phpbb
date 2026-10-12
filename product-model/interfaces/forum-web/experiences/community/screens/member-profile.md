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
        "Birthday",
        "Email",
        "Last active at",
        "Online presence"
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
      "forum-web": "memberlist.php?mode=viewprofile"
    }
  ]
}
---

# Member profile

The working context for member profile. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
