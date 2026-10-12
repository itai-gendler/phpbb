---
{
  "entities": [
    {
      "entity": "log-entry",
      "shows": [
        "Actor",
        "Operation",
        "Recorded at",
        "IP",
        "Category",
        "Subject",
        "Event information"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/mcp/mcp_logs.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/includes/acp/acp_logs.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "phpBB/phpbb/log/log.php"
    }
  ],
  "entryPoints": [
    {
      "forum-web": "mcp.php?i=logs"
    }
  ]
}
---

# Moderator logs

The working context for moderator logs. Displayed facts follow their disclosure rules. Collected input does not disclose stored credential or proof verifiers.
