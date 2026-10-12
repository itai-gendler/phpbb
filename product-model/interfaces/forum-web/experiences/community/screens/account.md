---
{
  "entities": [
    {
      "entity": "account",
      "shows": [
        "Username",
        "Email",
        "Profile values",
        "Birthday",
        "Preferred language",
        "Timezone",
        "Date format",
        "Style",
        "Allow private messages",
        "Allow email contact",
        "Allow mass email",
        "Online visibility",
        "Display options",
        "Censor preference",
        "Posting defaults",
        "Notification choices"
      ],
      "collects": [
        "Username",
        "Email",
        "Credential",
        "Profile values",
        "Birthday",
        "Preferred language",
        "Timezone",
        "Date format",
        "Style",
        "Allow private messages",
        "Allow email contact",
        "Allow mass email",
        "Online visibility",
        "Display options",
        "Censor preference",
        "Posting defaults",
        "Notification choices"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_profile.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_prefs.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/ucp/ucp_notifications.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/notification/method/board.php"
    }
  ],
  "entryPoints": [
    {
      "forum-web": "ucp.php?i=profile&mode=reg_details"
    }
  ]
}
---

# Account

The working context for account. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
